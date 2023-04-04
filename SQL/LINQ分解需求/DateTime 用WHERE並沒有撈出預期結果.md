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
```
var firstDate = new DateTime(2023,3,1);
var lastDate = new DateTime(2023,3,24);
model.Where(r => r.attr >= firstDate && r.attr <= lastDate)
```
# Question:
為何邏輯上沒有錯,但撈出結果並無預期呈現
# Answer:
仔細檢查發現DateTime細節是有到HH:mm:ss的,因此碰到這種可能limit可透過AddDay來處理