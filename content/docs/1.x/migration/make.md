---
title: "Make Migration"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 22
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Each database engine (dialect) has its own schema, so you need to specify the engine when creating a migration.

Example database engines: mysql, sqlite, mariadb, postgresql, clickhouse, redshift.

JetShift supports all [SQLAlchemy's Dialects](https://docs.sqlalchemy.org/en/20/dialects/). For ClickHouse, the dialect name is `clickhouse-sqlalchemy`. You can simply use `clickhouse` instead of the full dialect name. Ensure you use the same name when running migrations or creating seeders.

To create a new migration for a table, use the following command:

```bash
jetshift make migration table-name -e database-engine
```

Examples

```bash
jetshift make migration blogs # default engine is mysql
jetshift make migration blogs -e mysql
```
