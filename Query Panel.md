```dataview
table tags

from 
<<<<<<< HEAD
	#log/project or #event 
	and !"Templates"where 

date >= date(today) - dur(1 day)
=======
	#log/project/RFQ0645
	and !"Templates"
where 
	date >= date(today) - dur(15 day)
>>>>>>> 54b0301540b027002ca4d64566be546fc7f1783d
	
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