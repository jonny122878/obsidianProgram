where contains(Restructure, "") OR Qty > 7



```dataview 
TABLE Qty,Restructure,file.path
FROM "exception/集合exception"
where !contains(file.name,"Unify")
sort file.path
