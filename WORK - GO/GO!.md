```dataview
TABLE length(file.lists) AS "Trucks"
FROM "WORK - GO/Date"
SORT desc
WHERE length(filter(file.lists, (l) => !l.task))
```
