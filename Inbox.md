---
date: 2022-03-06
aliases: Inbox
tags:
---

```dataview
table aliases as Description, status
where date>=date(som) and date<=date(eom) and status="Inbox"
sort file.mtime desc
```

