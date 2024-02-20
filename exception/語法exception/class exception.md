# Metadata
Qty::5
Review::
Restructure::relation

### Think

# Exception


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


4. #flashcards 
- Highlight:python
- Question:為何再調用時內部bingoData屬性為空
```
	    bingoData = []
    def __init__(self,bingoData:[]):
        bingoData = bingoData
```
?
- Answer:可將其想成類typescript弱型別前面一定要有修飾子

5. #flashcards 
- Highlight:component內constructor injection service
- Question:發現接手code並無宣告相對應成員
?
- Answer:Angular語法糖省去C#宣告成員冗餘效果