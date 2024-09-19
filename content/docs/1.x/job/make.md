---
title: "Make Job"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 42
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Structure

```bash
jetshift make job job-name -jt job-type
```

Examples

```bash
jetshift make job time # default job type is simple
jetshift make job time -jt simple
```

You can find all available job types [here](https://github.com/jetshift/core/tree/main/jetshift_core/stubs/jobs).
