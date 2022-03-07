---
date: 2022-03-06
aliases: LunchBoxes
status: Inbox
tags:
---


```dataview
table aliases as Description
from #Lunchbox  
where status="archived"
sort file.mtime desc
```
