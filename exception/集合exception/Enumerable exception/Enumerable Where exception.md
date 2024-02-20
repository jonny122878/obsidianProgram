# Metadata
Qty::7
Review::
Restructure::relation 2~4

### Think



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
- Highlight:C#,在做存檔分別有主和子2個集合，要將子集合元素依序附加到主集合元素後存檔
```
//主集合
policyDrafts = policyDraftLists.Select(r =>
{
//子集合 查詢元素並附加
var policyRateAdjustModel = policyRateAdjustModels.FirstOrDefault(c => c.ScopeNo == r.ScopeNo &&
c.LocationNo == r.LocationNo );
//....
}).ToList();
```
- Question:為何存檔時明細都為相同元素
?
- Answer:PK有遺漏，導致數量從期望值為唯一筆變成多筆，

6. #flashcards 
- Highlight:C#
- Question:?.First  
?
- Answer:Sequence contains no elements

7. #flashcards 
- Highlight:C#
- Question:FirstOrDefault 是否會有延遲特性
?
- Answer:單一元素不會延遲
