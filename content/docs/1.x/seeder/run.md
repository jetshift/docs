---
title: "Run Seeder"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 103
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Structure

```bash
jetshift seed table-name -e database-engine -n number-of-records
```

### Run all seeders

```py {title="Examples"}
jetshift seed # default engine is mysql
jetshift seed -e mysql
```

### Run specific seeder

```bash
jetshift seed table-name -e database-engine
```

```py {title="Example"}
jetshift seed users # default engine is mysql
jetshift seed users -e mysql
```

### Run specific seeder with n records

```bash
jetshift seed table-name -e database-engine -n number-of-records
```

```py {title="Example"}
jetshift seed users -n 10 # default engine is mysql
jetshift seed users -e mysql -n 10
```
