---
data:2023-02-24
aliases
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project:租貸
Author:
Note Type:
Topics:Regular Expression

# Highlight:
AP存檔時丟出MS-SQL欄位與資料行數量不一致情況,要檢查確認是那個對照欄位出問題,因此將欄位與對應值切割成二個array
# Question:
發現在用Regular去捕捉字串時,並沒有辦法INSERT SQL整句整個用Regular抓取到string內
# Answer:
因為input 來源為string.Format() 所以其帶有\n符號,預設Regex是無匹配換行符的,
Regex = new Regex(re,RegexOptions.Singleline**);
實作語言[[Reg C語言]]
