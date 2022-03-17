```dataview
table tags

from 
	#log/project/RFQ0645
	and !"Templates"
where 
	date >= date(today) - dur(15 day)
	
sort date desc
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