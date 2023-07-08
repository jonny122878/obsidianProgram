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
#資料 
# Unify
- MS-SQL **function**本身不丟exception,可以想像成是弱型別,是透過丟出結果判別錯誤



1. #flashcards 
- Highlight:MS-SQL
- Question:SUBSTRING('test',0,1) 
?
- Answer:其都為字串,因此return **空字元**

2. #flashcards 
- Highlight:MS-SQL
- Question:當欄位為空字元調用SUBSTRING
?
- Answer:其都為字串,因此return **空字元**

3. #flashcards 
- Highlight:MS-SQL
- Question:aggrgate function ex:MAX、MIN，若此集合為空則return?
?
- Answer:其aggreagte input型態會有多種,因此用萬用型態**NULL**表達


4. #flashcards 
- Highlight:新增資料進行防呆時要檢查目前此筆資料為第幾版號
- Question:在LINQ中使用WHERE後MAX丟出exception
?
- Answer:MAX本身並無防呆NULL情境，從**名稱直覺**並無FirstOrDefault


5. #flashcards 
- Highlight:AVG在不同數字型態return?
- Question:小數點會依據型態做進位
?
- Answer:int計算出來值就不可能有小數位數值 

6. #flashcards 
- Highlight:
- Question:
?
- Answer:


