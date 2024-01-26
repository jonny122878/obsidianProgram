# Metadata
Qty::6
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突


- typescript變數和其在函數作用域和一般理解不同
- python JSON key和一般直覺不同



1. #flashcards 
- Highlight:typescript
- Question:interface明明是規範，為何可以實體化，是定義上有所不同?
?
- Answer:interface所理解定義和C#無差異，主要是因為其弱型別語言寬鬆特性，不用具名類別

2. #flashcards 
- Highlight:python
- Question:為何再調用時內部bingoData屬性為空
```
	    bingoData = []
    def __init__(self,bingoData:[]):
        bingoData = bingoData
```
?
- Answer:可將其想成類typescript弱型別前面一定要有修飾子

3. #flashcards 
- Highlight:要將陣列給塞入字典元素
```
arrBingo.insert({term:key,balls:value})
```
- Question:name 'term' is not defined
?
- Answer:和JSON直覺稍有不同，key要加引號

4. #flashcards 
- Highlight:component內constructor injection service
- Question:發現接手code並無宣告相對應成員
?
- Answer:Angular語法糖省去C#宣告成員冗餘效果

5. #flashcards 
- Highlight:python
- Question:調用物件丟出AttributeError 'Test' object has no attribute 'a'
?
- Answer:complier不會檢查object有無屬性,反之若沒有就幫你新增
```
result = test.a //無屬性exception
test.__b = 1 // 新增
```

6. #flashcards 
- Highlight:typescript
- Question:this.thirdStatus[index] == 'M';語法不excpetion也無指定值
?
- Answer:可想成調用bool函數沒return值一樣情況
