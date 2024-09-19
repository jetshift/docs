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
jetshift seed database-engine # run all jetshift seeders
jetshift seed database-engine table-name # run specific jetshift seeder
jetshift seed database-engine table-name -n number # run specific jetshift seeder with n records
```

Examples

```bash
jetshift seed mysql
jetshift seed mysql users
jetshift seed mysql users -n 10
```
