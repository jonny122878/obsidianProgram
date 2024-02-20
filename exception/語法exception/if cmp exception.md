# Metadata
Qty::8
Review::
Restructure::relation

### Think









# Exception



1. #flashcards 
- Highlight:typescript
- Question:不同型別之間是可以比較並無exception產出結果為?
?
- Answer:
```
7 > "test" => NaN
```

2. #flashcards 
- Highlight:typescript
- Question:字串做大小比較為何無異常?
?
- Answer:按照字母順序做比較基準，如果超過一個字元用字元順序開始比較
```
"a" > "b" => false
"test" > "tesz" => false
```

3. #flashcards 
- Highlight:typescript
- Question:條件式要擋掉不符合臨界值型別，能否用null擋全部
?
- Answer:只能用null、擋住undefined，內容相同都是空值，差別再於給使用者了解臨界狀態。NaN不表示空值只能用isNaN判別

4. #flashcards 
- Highlight:typescript。當新增狀態時，Output型別並無初始化，用if防呆
```
if(this.mainData.questionData.q04 != undefined)
```
- Question:Console一樣錯誤訊息
?
- Answer:物件本身才有用，其屬性無效
```
this.mainData.questionData undefined
this.mainData.questionData.q04 error
```

5. #flashcards 
- Highlight:typescript
- Question:條件式return 0
```
if (0 && !isNaN(Number(0))) return 0
if(object) //Angular特定情境也是0,目前無法判別
```
?
- Answer:目前還無法確定0定義?

6. #flashcards 
- Highlight:typescript 
- Question:條件式跳過判別
```
if(''.match(pattern)) 
```
?
- Answer:無考量到null,且只要不是true都會跳開

7. #flashcards 
- Highlight:combobox select value為數字
- Question:為何防呆條件無法成立
?
- Answer:語法錯誤，javascript特性無丟exception
```
(result.clauseType == 2) ? false:true; //ok
(result.clauseType = 2) ? false:true;  //error
```

8. #flashcards 
- Highlight:typescript
- Question:FormControl value為string 和if內數字進行運算會產生何種結果
?
- Answer:其會自動轉數字
```
('10' > 3) true
('10' < 3) false
```




  