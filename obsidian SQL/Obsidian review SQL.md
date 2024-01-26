where !contains(file.path,"tasker")  //檢查是否有尚未移動workflow
where contains(file.name,"exception") 
FROM #work AND !(#資料 OR #資訊 OR #知識)  //找出要提煉
FROM #work AND #知識 //找出要提煉
TABLE file.name,file.mtime,Qty,file.tags,file.path
sort file.mtime desc
limit 5

早上要進行復歸，或將有問題挑出photo sort Review、資訊、資料
TABLE file.mtime,Qty,file.tags,Review
FROM #work AND (#資料 OR #資訊 OR #知識)
sort Review desc,file.mtime desc


1月沒mtime 知識變資訊 :(放寬2月)
TABLE file.mtime,Qty,file.tags,Review
FROM #work AND #知識
sort file.mtime asc
limit 12




```dataview 
TABLE file.mtime,Qty,file.tags,Review,Restructure
FROM #work AND (#資料 OR #資訊 OR #知識)
sort Review desc,file.mtime desc
