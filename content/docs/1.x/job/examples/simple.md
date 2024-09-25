---
title: "Simple Job"
description: "This is a simple job that prints the current date and time."
summary: ""
date: 2024-09-24T16:13:18+02:00
lastmod: 2024-09-24T16:13:18+02:00
draft: false
weight: 161
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

This is a simple job that prints the current date and time.

```python {title="jobs/simple.py"}
from config.luigi import luigi, local_scheduler
from datetime import datetime

class SimpleJob(luigi.Task):
    def run(self):
        formatted_time = datetime.now().strftime('%b %d, %Y %I:%M %p')
        message = f'Date and time: {formatted_time}'
        print(message)

        # Mark task as completed
        self.task_completed = True

    def complete(self):
        return getattr(self, 'task_completed', False)

def main():
    luigi.build([SimpleJob()], local_scheduler=local_scheduler)

if __name__ == '__main__':
    main()
```
