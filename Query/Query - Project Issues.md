```dataview
table tags, status
from #log/project/MiTAC   and !"Templates"
where status!="close"
sort date desc
```



```
[list|task|table field1, (field2 + field3) as myfield, ..., fieldN]
from #tag or 'folder'
where field [>|>=|<|<=|=|&|'|'] [field2|literal value] (and field2 ...) (or field3...)
sort field [asc|desc]
```