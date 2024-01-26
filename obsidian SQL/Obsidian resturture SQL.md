-- 要整理掉
TABLE file.name,file.mtime,file.tags,file.path
FROM #py

資料夾超過7重新分類
exception7超過重新分類
note一定要有關聯

1個note會有多個錯誤特性，因此不用特別移動，關聯標註即可


```dataview 
TABLE file.name,file.mtime,file.tags,file.path,Qty
FROM "tasker/轉型exception"
sort Qty desc


