
TABLE Qty,Restructure,file.mtime
FROM "exception/型別exception"

table length(rows.file)
from "exception/型別exception"
group by file.folder


```dataview
TABLE Qty,Restructure,file.mtime
FROM "exception/型別exception"
WHERE !contains(file.name,"Unify") And !contains(file.name,"apply")
sort Restructure
