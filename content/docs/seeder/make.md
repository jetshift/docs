---
title: "Make Seeder"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 31
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Structure

```bash
make seeder seeder-name -e database-engine
```

Examples

```bash
make seeder blogs # default engine is mysql
make seeder blogs -e mysql
```

Available database engines: mysql. You can easily add new a engine.

All seeders are available in `database/seeders` directory.
