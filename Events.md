[[Archived]]

---

```dataview
table aliases as Description
from #event 
where status="archived"
sort file.mtime desc
```