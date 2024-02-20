# Metadata
Qty::3
Review::
Restructure::relation 1~3

### Think


# Exception


1. #flashcards 
- Highlight:
- Question:撈取INSERT SQL欄位區段撈不到
```
([\w]+)
```
?
- Answer:C#,撈取INSERT SQL值區段撈不到
  - 釐清特殊字元定義，ex:() 刮弧就是特殊字元
  - 釐清那些是符號規範,ex:,逗號就不在\w類別尺度內
  - 解法所能接受符號自己包覆成類別尺度,並且特殊符號前面要加修飾子
```
\([\w,+]\)
```

2. #flashcards 
- Highlight:C#,撈取INSERT SQL值區段撈不到
- Question:因值區段包含眾多符號,規劃用萬用字元.去抓
```
(.*\)
```
?
- Answer:
  - .萬用字元順序>)，因此整個就停不下直接到結尾
  - 釐清那些是特殊符號,那些是不包含\w符號需要自己用做成**類別尺度[]**

3. #flashcards 
- Highlight:javascript
- Question:怎樣都攔到
```
/\d+.\d+/ 
```
?
- Answer:注意關鍵字是否有加入特殊修飾字元辦識
