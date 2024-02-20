# Metadata
Qty::3
Review::
Restructure::

### Think

# Exception
 

1. #flashcards 
- Highlight:C#
- Question:SubString(8)截斷結果?
?
- Answer:從第8字元**順序開始**截斷,~~從順序0字元開始取8個字元~~

2. #flashcards 
- Highlight:javascript
- Question:在調用replace時是否能像理解C# replace
?
- Answer:JavaScript的replace()函數默認是**不區分大小寫**的。如果您需要在JavaScript中區分大小寫，可以使用**正則**表達式來實現，其他相關規則也通用
類似用C# replace全字串取代
```
replace(/,/g, '')
```

3. #flashcards 
- Highlight:C#
- Question:Split:做字串分割目標物若在字尾最後字元,會產出幾個陣列?
?
- Answer:分割目標會被吃掉後產出2個元素陣列，不是~~1個元素陣列~~
  ```
  var file = @"D:\test\test.txtz";
  var split = file.Split('z');
  ```


