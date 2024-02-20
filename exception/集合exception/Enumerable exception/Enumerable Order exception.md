# Metadata
Qty::4
Review::
Restructure::

### Think



# Exception


1. #flashcards 
- Highlight:LINQ
- Question:為何ThenBy只能接再OrderBy之後?
?
- Answer:因為ThenBy是調用IOrderEnumerable，其是透過OrderBy return 

2. #flashcards 
- Highlight:javascript
- Question:如何透過sort函數達到升序或降序
?
- Answer:函數編程風格透過**數學**方式達到升、降序效果
```
myArray.sort(function(a, b) { return a - b; });
a - b ASC
b - a DESC
```
推論條件式a - b 前面比較小就符合，因此為升序

3. #flashcards 
- Highlight:原本附件檔案會分別存放在三個路徑中其中一個路徑，需求是要將目前所存放檔案給移轉到另個位置
- Question:分析解法是透過LINQ GROUP BY以檔案為Key，路徑為Enumerable，透過此方式ORDER BY用檔案是否存在bool當條件，取最前面的，產出不如預期
?
- Answer:直覺true > false，但實際false > true

4. #flashcards 
- Highlight:typescript
- Question:如何進行ThenBy?
?
- Answer:無內建ThenBy，目前還再研究，下面範例為自定義Object要透過override sort 搭配if模擬
```
let sortBaseRateFeeQueryResultModels = baseRateFeeQueryResultModels.sort((a,b) =>
            {
              let cmp1 = a.strCol1.localeCompare(b.strCol1);
              if(cmp1 != 0)
              {
                return cmp1;
              }
              let cmp2 = a.strCol2.localeCompare(b.strCol2);
              if(cmp2 != 0)
              {
                return cmp2;
              }
              return a.strCol3.localeCompare(b.strCol3);
            });
```

5. #flashcards 
- Highlight:
- Question:
?
- Answer: