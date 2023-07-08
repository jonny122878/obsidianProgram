where contains(Topics,"review") 
where contains(file.name,"exception") 


```dataview 
TABLE file.name,file.mtime,Topics,file.tags
FROM "4_SQL" 

