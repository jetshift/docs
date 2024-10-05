---
title: "Make Seeder"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 102
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

No need to create separate seeder files for each table. Seeder is available in the migration file. JetShift auto generate fake data based on the column type. You can just run the seeder command to seed the data.

### Faker and Random Functions

JetShift supports Python's faker and random functions to generate fake data.

#### Faker Functions

You can define custom faker data in the migration file. You need to add the `seeder` key in the column definition. The seeder key value should be a valid faker function.

Python faker library is used to generate fake data. You can find the list of [faker functions here](https://faker.readthedocs.io/en/master/index.html).

```yaml {title="app/migrations/users.yaml", hl_lines=[6,11]}
table_name: users
columns:
  - name: name
    type: VARCHAR(199)
    nullable: true
    seeder: fake.name()

  - name: email
    type: VARCHAR(199)
    nullable: true
    seeder: fake.email()
```

#### Random Functions

JetShift also supports [Python's random module functions](https://docs.python.org/3/library/random.html). You can use the random module functions as a seeder value.

```yaml {title="app/migrations/users.yaml", hl_lines=[6,11]}
table_name: users
columns:
  - name: age
    type: INT
    nullable: true
    seeder: random.randint(18, 60)

  - name: status
    type: VARCHAR(25)
    nullable: false
    seeder: random.choice(['active', 'inactive'])
```

### Load Fake Data from CSV

You can also load fake data from a CSV file. To do this, you need to add `seeders` directory in the `app/migrations` directory.

Create a CSV file with the same name as the table name. The CSV file should contain the required column names in the first row.

```cmd {title="app/migrations/seeders/users.csv"}
id,name,email
1,Jennifer Velez,stevenmoore@bowers.info
2,Suzanne Baker,alexanderjackson@jackson.com
3,Erica Wallace,johnsonjoshua@anderson.com
4,Gregory Cannon,joshuaallen@martinez.com
5,Susan Campbell,yhicks@hotmail.com
```

Now, you need to add the `data` key in the migration file and set it to `true`.

```yaml {title="app/migrations/users.yaml", hl_lines=2}
table_name: users
data: true
columns:
  - name: id
    type: INT
    primary_key: true
    auto_increment: true
```
