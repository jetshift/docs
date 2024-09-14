---
title: "Make Migration"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 21
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Structure
```bash
make migration table-name -e database-engine
```

Example
```bash
make migration blogs # default engine is mysql
make migration blogs -e mysql
```


Available database engines: mysql, clickhouse. You can easily add new a engine.

All migrations are available in `database/migrations` directory.
