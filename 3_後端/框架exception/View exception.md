
---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::4
#side 

# Unify




1. #flashcards 
- Highlight:View
- Question:確定Controller內撈出Model有資料,並且@model 轉型型別也沒出錯,為何會丟出**Object reference not set to an instance of an object**
?
- Answer:.cshtml中修飾子@page會跟@model衝突

2. #flashcards 
- Highlight:View
- Question:the ViewDataDictionary instance requires a model item of type ToList()
?
- Answer:為了EF效能最後在呈現時遺漏做實體化

3. #flashcards 
- Highlight:View
- Question:View An error occurred while processing youre request Request ID:..... 
?
- Answer:View Prase Model傳來**object**並無按照原本型別去Prase

4. #flashcards 
- Highlight:jQuery
- Question:為何jQuery明明按照format日期格式填入,但實際運行無效果
```
<input type="date" asp-format="yyyy/MM/dd" >
$('#').val('2023/03/17')
```
?
- Answer:日期格式只有一種yyyy-MM-dd標準弱型別格式
asp-format格式是用來**顯示**

5. #flashcards 
- Highlight:
- Question:
?
- Answer:

