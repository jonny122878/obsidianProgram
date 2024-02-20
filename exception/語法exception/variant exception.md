# Metadata
Qty::5
Review::
Restructure::relation

### Think

1. #flashcards 
- Highlight:typescript
- Question:interface明明是規範，為何可以實體化，是定義上有所不同?
?
- Answer:interface所理解定義和C#無差異，主要是因為其弱型別語言寬鬆特性，不用具名類別

2. #flashcards 
- Highlight:要將陣列給塞入字典元素
```
arrBingo.insert({term:key,balls:value})
```
- Question:name 'term' is not defined
?
- Answer:和JSON直覺稍有不同，key要加引號

3. #flashcards 
- Highlight:python
- Question:調用物件丟出AttributeError 'Test' object has no attribute 'a'
?
- Answer:complier不會檢查object有無屬性,反之若沒有就幫你新增
```
result = test.a //無屬性exception
test.__b = 1 // 新增
```

4. #flashcards 
- Highlight:typescript
- Question:this.thirdStatus[index] == 'M';語法不excpetion也無指定值
?
- Answer:可想成調用bool函數沒return值一樣情況

5. #flashcards 
- Highlight將原本結構轉換成類似C匿名型別字典後，進行調用
- Question:調用字典內不存在屬性為何無丟錯
?
- Answer:字典語法錯誤，javascript特性無丟exception
```
map ....
{address:r,scope:c.scopeList[0]}
let address = r.address.locationName;
```