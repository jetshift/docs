---
title: "Migration"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 51
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Database migration is the process of managing and applying changes to the database schema over time. This includes creating, altering, and deleting database tables and other objects.

We use [SQLAlchemy](https://www.sqlalchemy.org/) library. SQLAlchemy provides database-agnostic support for creating and manipulating tables across various [supported database systems](https://docs.sqlalchemy.org/en/20/dialects/). Typically, migrations will use this library to create and modify database tables and columns.


All migrations are available in `database/migrations` directory.
