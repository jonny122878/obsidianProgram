```dataview
TABLE Qty,Restructure,file.path
FROM "exception/語法exception"
where !contains(file.name,"Unify")
