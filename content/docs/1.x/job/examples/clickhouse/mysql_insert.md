---
title: "MySQL to ClickHouse (Insert)"
description: "Transfer millions of rows from MySQL to ClickHouse."
summary: ""
date: 2024-09-24T16:13:18+02:00
lastmod: 2024-09-24T16:13:18+02:00
draft: false
weight: 181
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Transfer millions of rows from MySQL to ClickHouse.

```python {title="jobs/users.py"}
from config.luigi import luigi, local_scheduler
from jetshift_core.tasks.mysql_clickhouse_insert import BaseTask

class UsersETL(BaseTask):
    table_name = 'users'

def main():
    luigi.build([UsersETL(
        live_schema=False,
        primary_id='id',
        # extract
        extract_offset=0,
        extract_limit=500,
        # extract_chunk_size=500,
        # load
        truncate_table=False,
        load_chunk_size=500,
        sleep_interval=5
    )], local_scheduler=local_scheduler)

if __name__ == '__main__':
    main()
```

### Parameters

| Parameter          | Default       |
|--------------------|---------------|
| live_schema        | False         |
| primary_id         | None          |
| extract_offset     | 0             |
| extract_limit      | 0             |
| extract_chunk_size | 1000          |
| truncate_table     | False         |
| load_chunk_size    | 1000          |
| sleep_interval     | 1 (in second) |

### live_schema

`False` means take table's schema from database. `False` means take schema from local (`databases/migrations/mysql/users.py`) file.

If your live database table has many columns but you want to transfer only few columns to warehouse then you can use `False` and define only required columns in local file.

### primary_id

Primary id column will be used for offsetting the extract query.

```python
primary_id='id'

SELECT * FROM {table_name} WHERE {primary_id} > {extract_offset}
```

### extract_offset

If we want to extract data those are greater than id, then we can use `extract_offset`.

```python
extract_offset=100

SELECT * FROM {table_name} WHERE {primary_id} > {extract_offset}
```

### extract_limit

To reduce the pressure on source database, we can use `extract_limit`.

```python
extract_limit=500

SELECT * FROM {table_name}
WHERE {primary_id} > {extract_offset}
LIMIT {extract_limit}
```

if we set `extract_limit=500` then it will extract only 500 rows and stop the job.

This is useful when we want to transfer a small amount of data or test the job with a few rows.

### extract_chunk_size

Extract chunk size is used to extract data in chunks. This is useful when we have millions of rows in the source table. It works similar to `extract_limit` but it will extract data in chunks.

```python
extract_chunk_size = 1000

# will auto calculate total rows and loops.
# then extract data in chunks with sleep interval.

```python
total_rows = 100000
total_loops = total_rows / extract_chunk_size

for i in range(total_loops):
    offset = (i * extract_chunk_size) + extract_offset
    query = f"SELECT * FROM {table_name}
              WHERE {primary_id} > {extract_offset}
              LIMIT {extract_chunk_size}
              OFFSET {offset}"
    time.sleep(sleep_interval)
```

We cannot use `extract_limit` and `extract_chunk_size` together. If we set `extract_limit` then `extract_chunk_size` will be ignored.

### truncate_table

If we want to truncate the table before loading to the target, we can use `truncate_table=True`.

### load_chunk_size

Load chunk size is used to load data in chunks. This is useful when we have millions of rows in the source table. It works similar to `extract_chunk_size` but it will load data in chunks.

### sleep_interval

Sleep interval is used to pause the job for a few seconds. This is useful when we have a large number of rows in the source table and we want to reduce the pressure on the source and target databases.
