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


- 疑惑點:([\w]+)
- 情境:再撈取INSERT SQL欄位區段撈不到
- 判別:
  - 釐清特殊字元定義，ex:() 刮弧就是特殊字元
  - 釐清那些是符號規範,ex:,逗號就不在\w類別尺度內
  - 解法所能接受符號自己包覆成類別尺度,並且特殊符號前面要加修飾子
  - \([\w,+]\)

- 疑惑點:因值區段包含眾多符號,規劃用萬用字元.去抓 ex: (.*\)
- 情境:再撈取INSERT SQL值區段撈不到
- 判別:
  - .萬用字元順序>)，因此整個就停不下直接到結尾
  - 釐清那些是特殊符號,那些是不包含\w符號需要自己用做成**類別尺度[]**
  
  
- 疑惑點:調用re.test()怎樣都無法調用
- 情境:js Regular Expression
- 判別:注意指定re是否有用成string,Regular Expression是一種型別,只需re =/pattern/

- 疑惑點:/\d+.\d+/ 怎樣都攔到
- 情境:
- 判別:注意關鍵字是否有加入特殊修飾字元辦識
