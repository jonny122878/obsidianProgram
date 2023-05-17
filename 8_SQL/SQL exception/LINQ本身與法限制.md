---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:
1.
# Question:
1.為何DataTable要用複合key都呈現紅字
2.匿名型別無法用陳述式JOIN
# Answer:
1.語法規範，DataTable AsEnumerable表達和陳述式都不能用複合key
```
on new { inner.Key, inner.Value } equals new { outer.Key, outer.Value }
```
2.語法規範
- There is already an open DataReader associated with this Command which must be closed first?
  - EF集合沒有用Extension讓其支援標準運算，ex:ToList() 

- 疑惑點:JOIN不出結果
- 情境:建立一個DB參數集合與UI元件集合要將二者關聯後UI值填入參數
- 判別:檢查後面是否有ToList之類實體化,此現象因LINQ有**延遲效果**
