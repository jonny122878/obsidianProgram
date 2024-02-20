where contains(Restructure, "") OR Qty > 7

研究怎針對資料夾group找出超過7個
怎麼sum Qty


```dataview 
TABLE Qty,Restructure
FROM "exception/集合exception"
where contains(file.name,"exception")
sort Restructure
