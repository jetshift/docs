---
title: "Run Seeder"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 33
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Structure

```bash
seed database-engine # run all seeders
seed database-engine table-name # run specific seeder
seed database-engine table-name -n number # run specific seeder with n records
```

Examples

```bash
seed mysql
seed mysql users
seed mysql users -n 10
```
