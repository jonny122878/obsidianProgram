# Metadata
Qty::5
Review::
Restructure::relation、summary

#work #資訊 
# Unify

## 本質

## 衍生衝突

# Exception


1. #flashcards 
- Highlight:LINQ
```
var firstDate = new DateTime(2023,3,1);
var lastDate = new DateTime(2023,3,24);
model.Where(r => r.attr >= firstDate && r.attr <= lastDate)
```
- Question:DateTime 為何邏輯上沒有錯,但撈出結果並無預期呈現
?
- Answer:仔細檢查發現DateTime細節是有到HH:mm:ss的,因此碰到這種可能limit可透過AddDay來處理

2. #flashcards 
- Highlight:typescript
- Question:Uncaught **TypeError**:object Array is not a function
?
- Answer:函式理解調用錯誤,dataArr.filter(dataArr,function(e){})


3. #flashcards 
- Highlight:javascript
- Question:調用function some時做防呆時不管甚麼情境都是return false
?
- Answer:弱型別特性，語法**遺漏return** ....導致都為default


4. #flashcards 
- Highlight:javascript 做測試資料進行防呆測試
```
let isExist = this.addresses.some(r => r.value == this.quoteThirdData.quoteAddress[i].locationName);
```
- Question:無按照some去跑?
?
- Answer:並無特別指定屬性所導致
```
let addr2 = <QuoteAddress>
        {
            quoteNo:'',
            quoteVer:1,
            locationNo:'005',
            fullAddress:'test',
        };
```

5. #flashcards 
- Highlight:typescript
- Question:splice使用時機
?
- Answer:其有點類似take、skip之類放置where參數指定索引與長度
```
// 删除元素示例 
const deletedElements = array.splice(2, 2); 
console.log(array); // 输出: [1, 2, 5] 
console.log(deletedElements); // 输出: [3, 4]
```


