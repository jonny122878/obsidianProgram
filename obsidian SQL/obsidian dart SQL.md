```dataview
TABLE file.name,file.mtime,Qty,file.path
FROM #dart
where !contains(file.path,"tasker") 
