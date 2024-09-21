---
title: "Installation"
description: "Guides lead a user through a specific task they want to accomplish, often with a sequence of steps."
summary: ""
date: 2023-09-13T16:04:48+02:00
lastmod: 2023-09-13T16:04:48+02:00
draft: false
weight: 12
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Getting started is easy. Follow these steps to install and set up the project.

First, clone the repository:

```bash
git clone --depth 1 git@github.com:mdobydullah/jetshift.git
```

Then, navigate to the project directory:

```bash
cd jetshift
```

Copy the environment file:

```bash
cp .env.example .env
```

You can run the project with docker and without docker.

### With Docker

To run the project with docker, run the following command

```bash
docker compose up -d
```

Web servers

```bash
Web: http://localhost:8080
Luigid: http://localhost:8082
```

### Without Docker

Install Python on your machine and create virtual environment

```bash
python -m venv venv
```

Activate the virtual environment

```bash
# linux
source venv/bin/activate

# windows
venv\Scripts\activate

# windows (gitbash)
source venv/Scripts/activate
```

Install requirements

```bash
pip install -e .
```

Run dev servers

```bash
jetshift dev
```

Web servers

```bash
Web: http://localhost:8080
Luigid: http://localhost:8082
```
