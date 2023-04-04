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

# Question:
@model IEnumerable 是**集合**,但**欄位名是元素**相衝突,該如何綁定
# Answer:
透過FirstOrDefault將**集合轉成元素**投射到表格欄位名上
```
@Html.DisplayNameFor(r => Model.FirstOrDefault(c => c.attr))
```
表格值是集合因此**不用轉換**用foreach展開
```
@foreach(var item in Model)
{
	@Html.DisplayFor(r => item.attr)
	...
}
```
