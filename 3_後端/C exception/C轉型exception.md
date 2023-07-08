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

# Unify





1. #flashcards 
- Highlight:
- Question:
?
- Answer:

2. #flashcards 
- Highlight:
- Question:
?
- Answer:

3. #flashcards 
- Highlight:
- Question:
?
- Answer:

# Highlight:
1. 在API中將new隱含型別或各種具名參考型別class給傳入，Prase string to json之後，在透過 dynamic 接收 json prase class
2. 欄位序號編碼要轉成數字後再去作流水號增加
# Question:
1.
- 若dynamic接收變數若調用不存在的屬性編譯器會檢查嗎?
- new隱含型別此種編譯器製造出來型別是否能Prase
2. 002此種字串是否需要先將前面0給移除?
# Answer:
1. 
- 不會檢查，還原之後看編譯器型別為JSON OBJECT
- new隱含型別因是編譯器製造出來每次都不相同，還原之後就是string
2.int.TryPrase可直接轉型