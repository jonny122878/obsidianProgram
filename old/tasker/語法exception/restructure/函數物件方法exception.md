# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::3
Review::

#知識  #py 
# Unify
- python、typescript此種類弱型別語言封裝成類別屬性一定要明確修飾子
- python class def獨特有self
- python換行是有意義的， return 左刮弧不能換行，若保險用IDE換行
- 問題圍繞在keyword理解

1. #flashcards 
- Highlight:
- Question:為何import後還是會exception
```
import db
dbContext = MongoDbContext( "localhost", "test_db") //error
```
?
- Answer:前面要再加import修飾子
```
dbContext = db.MongoDbContext( "localhost", "test_db")
```


2. #flashcards 
- Highlight:python
- Question:封裝成類後函數調用一直無法調用，跳出需要二個參數
```
def calcu(input:[]):
```

?
- Answer:class時method不管有無函數都要有self


3. #flashcards 
- Highlight:python
- Question:method 函數再調用接收變數值，但明明有值一直return None
```
return 
{
            'support' :support,
            'maxValue' :maxValue,
            'median_value' :median_value,
}

```
?
- Answer:注意上刮號，可用排版解決


6. #flashcards 
- Highlight:
- Question:
?
- Answer: