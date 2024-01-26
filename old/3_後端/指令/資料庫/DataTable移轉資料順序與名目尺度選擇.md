---
data:2023-03-16
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
原本GridView呈現資料要將其移轉為千分位,因此來源DataTable需在做出一個DataTable呈現千分位
# Question:
原本使用順序尺度將資料移轉計算
ex:
```
arr[0] = ....
arr[1] = 千分位
dt.Row.Add(arr);
```
當下沒問題,但隨著欄位擴充時就有可能因順序變化而丟exception
ex:
```
dt.Column.Add(千分位) ...
dt.Column.Add() ...
```
千分位欄位**順序往前推移**,導致整個計算邏輯都要修正
# Answer:
較好方法選擇名目尺度,未來維護時不會因欄位擴充而變化
ex:
```
foreach(DataColumn col in row.Table.Columns)
```


