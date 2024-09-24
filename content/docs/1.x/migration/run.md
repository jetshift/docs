---
title: "Run Migration"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 23
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

### Run all migrations

```bash
jetshift migrate -e database-engine
```

```py {title="Examples"}
jetshift migrate # default engine is mysql
jetshift migrate -e clickhouse
```

### Run specific migration

```bash
jetshift migrate table-name -e database-engine
```

```py {title="Examples"}
jetshift migrate users # default engine is mysql
jetshift migrate users -e clickhouse
```

### Drop table and migrate

The `--fresh` or `-f` option will drop the table from the database and then execute the migrate command:

Drop all tables:

```bash
jetshift migrate --fresh # default engine is mysql
jetshift migrate -e clickhouse -f
```

Drop specific table:

```py {title="Examples"}
jetshift migrate users --fresh # default engine is mysql
jetshift migrate users -e clickhouse -f
```
