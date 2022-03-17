```dataview
table tags

from 
	#log/project or #event 
	and !"Templates"where 

date >= date(today) - dur(1 day)
	
sort file.mtime desc
```

常用語法

```
table tags

from 
	#log/project
	and !"Templates"

where 
	date >= date(today) - dur(1 month)
	date >= date(today) - dur(1 day)

sort date desc

```