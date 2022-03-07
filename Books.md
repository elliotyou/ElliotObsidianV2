---
date: 2022-03-06
aliases: Books
status: Inbox
tags:
---

```dataview
table aliases as Description
from #Books
where status="archived"
sort file.mtime desc
```
