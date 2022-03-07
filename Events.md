---
date: 2022-03-06
aliases: Events
status: archived
tags:
---

```dataview
table aliases as Description
from #event 
where status="archived"
sort file.mtime desc
```

