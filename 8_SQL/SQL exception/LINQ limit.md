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
1.在調用自訂義RowCommand時其為一組string[]，將其
```
arr.Select(r => r[0])
```
# Question:
產出結果很奇怪都為**數字**
# Answer:
1.因為當在做單一string時會自動理解成
```
IEnumerable<char>
```
因此產出原本產出數字結果為字元