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
INSERT INTO SQL丟出標題錯誤訊息
# Answer:
numeric規範:
   - 了解小數位數,ex:numeric(6,4)表示最少要保留四位小數位數
   - 183.481 因小數位數保留4位 complier翻成183.4810 exception
   - 因此推算**整數**位只能是2位
   - 確保讓使用者輸入長度也要有限制
int規範:
   - 在INSERT語法上8 是會exception
   - 8.0 表示有小數位