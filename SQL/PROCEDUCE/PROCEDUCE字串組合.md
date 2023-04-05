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
PROCEDUCE去計算資料，因為資料庫名稱為變數，所以將多段SQL弄成string後去執行
# Question:
EXECTE後一直出現exception
# Answer:
string在組合時，良好習慣頭尾要加**空字元**，免於掉入 SELECTFROM 這類keyword無間隔情況
檔組合內變數時，外部要在加字串修飾符
```
'' + @variant + ''
```

