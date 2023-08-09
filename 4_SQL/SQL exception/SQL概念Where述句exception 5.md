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
#資訊 

# Unify




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
- Highlight:MS-SQL附件檔案要搬移，需要針對單號欄位編碼移動位置判別，但有的單號為空白
- Question:解法方式想要寫法精簡，透過短路式先行判別長度後後在截斷字串
```
len > ... substring ...  //或是
WHERE IS NOT NULL <> ''
```
?
- Answer:
- MS-SQL計算原理為先計算一層後，在透過此層在前推一層，而不是二個條件推一層
ex:
100 => LEN() >  => 10 => substring => 5
按照如上原理，因無過濾因此還是丟exception

3. #flashcards 
- Highlight:
- Question:調用function some時做防呆時不管甚麼情境都是return false
?
- Answer:弱型別特性，語法**遺漏return** ....導致都為default


4. #flashcards 
- Highlight:做測試資料進行防呆測試
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

6. #flashcards 
- Highlight:
- Question:
?
- Answer:
- 
