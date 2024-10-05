---
title: "Job"
description: "Reference pages are ideal for outlining how things work in terse and clear terms."
summary: ""
date: 2024-09-13T16:13:18+02:00
lastmod: 2024-09-13T16:13:18+02:00
draft: false
weight: 151
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

The job is the ETL (Extract, Transform, Load) process. The job is a sequence of tasks that are executed in a specific order. The job is a way to automate the data processing. The job can be scheduled to run at a specific time or can be triggered by an event.

For scheduled jobs, you can use our built-in crontab scheduler. You can also use the API to trigger the job.

We use [Spotify's Luigi](https://github.com/spotify/luigi) to manage the job. Luigi is a Python module that helps you build complex pipelines of batch jobs. It handles dependency resolution, workflow management, visualization, and more.

All jobs are available in `app/jobs` directory.
