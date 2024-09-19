---
title: "Quicker"
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

Quicker is a set of commands that help you with migrations, seeders, and jobs. This is very helpful when you are making a report or testing your application. You can run all the commands in one go.

All quickers are available in `quickers` directory.

An example quicker:


```python {title="quickers/test.py"}
from jetshift_core.helpers.quicker import migrations, seeders, jobs


def main():
    migrations_list = ["mysql", "clickhouse"]
    migrations(migrations_list)
    print("\nMigrations completed ✓✓✓\n")

    seeder_list = ["users -n 10"]
    seeders(seeder_list)
    print("\nSeeders completed ✓✓✓\n")

    job_list = ["users"]
    jobs(job_list)
    print("\nJobs completed ✓✓✓\n")


if __name__ == "__main__":
    main()

```

