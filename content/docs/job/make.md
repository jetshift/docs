---
title: "Make Job"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 41
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Structure

```bash
make job job-name -jt job-type
```

Examples

```bash
make job time # default job type is simple
make job time -jt simple
```

Available job types: simple. You can easily add new a type.

All jobs are available in `jobs` directory.