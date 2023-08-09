結構發散3、查詢發散5、
where contains(Topics,"review") 
where contains(file.name,"exception") 
where contains(file.name,"exception") 
FROM "2_前端" 
and (contains(file.name,"述句") or contains(file.name,"函數"))
TABLE file.name,file.mtime,Topics,file.tags

```dataview 
TABLE file.name,file.mtime,file.tags,file.path
FROM #py
where !contains(file.path,"tasker") 


