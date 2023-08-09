where !contains(file.path,"tasker")  //檢查是否有尚未移動workflow
where contains(file.name,"exception") 
FROM #work AND !(#資料 OR #資訊 OR #知識)  //找出要提煉
FROM #work AND #知識 //找出要提煉
```dataview 
TABLE file.name,file.mtime,Qty,file.tags,file.path
FROM #work AND !(#資料 OR #資訊 OR #知識)


