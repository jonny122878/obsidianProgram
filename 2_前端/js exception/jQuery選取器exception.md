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

#資訊 

# Unify





1. #flashcards 
- Highlight:
- Question:TypeError Failed to construct FormData parameter 1 is not of type HTMLFormElement
?
- Answer:型態理解有問題，選擇器選出來是**jQuery獨特物件集合**，取HTMLFormElement需加index

2. #flashcards 
- Highlight:做分頁功能將目前html的table給清空之後重新建立DOM
- Question:table empty clear appendTo都無效,
?
- Answer:選取器應是要選到表格內容**tbody**
```
$('#') 造成連標題都清空
$('# tbody')
```

3. #flashcards 
- Highlight:ASP.NET內style設定display，透過判別業務邏輯是否隱藏將removeAttr
- Question:為何返還效果不同
?
- Answer:ASP.NET本身在Prase時會將一些屬性弄在style上，ex:TextBox Width，
因此這種情況比較適合用class

4. #flashcards 
- Highlight:選取器丟入$.each來源進行展開
- Question:進行元素$選取器方法無法做操作
?
- Answer:選取器可將其想成是一個**集合**，展開後元素型態會是**HtmlElement**


5. #flashcards 
- Highlight:
- Question:
?
- Answer:
