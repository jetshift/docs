---
title: "Quicker"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 501
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Quicker is a set of commands that help you with migrations, seeders, and jobs. This is very helpful when you are making a report or testing your application. You can run all the commands in one go.

All quickers are available in `app/quickers` directory.

An example quicker:

```yaml {title="app/quickers/test.yaml"}
migrations:
  fresh: true
  engines:
    - "mysql"
    - "clickhouse"

seeders:
  engines:
    - "mysql"
    - "clickhouse"
  names:
    - "users -n 50"
    #  - "all"

jobs:
  - "users"
  #  - "all"
  #  - "seeders"

```

The quicker will drop all the tables, run migrations, seeders, and jobs in one go.
