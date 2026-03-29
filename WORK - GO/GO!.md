## March
```dataview
TABLE 
    dv_Trucks AS "Trucks", 
    choice(out AND in, out - in, "?") AS "ODO", 
    OT
FROM "WORK - GO/Date"
SORT file.name DESC
```
