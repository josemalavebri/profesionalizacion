
```dataview
table
  dateformat(file.ctime, "dd/MM/yy") as "Fecha Creación"
from "Notes"
where contains(file.tags, "#estado-investigar")
sort file.ctime asc

```
