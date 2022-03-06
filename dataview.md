[[Obsidian]]

---

搜尋 Youtube → "# 用obsidian的kanban和dataview来管理卡片写作"

有在教安裝

[blacksmithgu/obsidian-dataview: A high-performance data index and query language over Markdown files, for https://obsidian.md/. (github.com)](https://github.com/blacksmithgu/obsidian-dataview)

[Dataview (blacksmithgu.github.io)](https://blacksmithgu.github.io/obsidian-dataview/)

```
輸出格式 欄名
from [#tag 或 資料夾]
where 條件
sort 欄位 [排序]
```

```
[list|task|table field1, (field2 + field3) as myfield, ..., fieldN]
from #tag or 'folder'
where field [>|>=|<|<=|=|&|'|'] [field2|literal value] (and field2 ...) (or field3...)
sort field [asc|desc]
```