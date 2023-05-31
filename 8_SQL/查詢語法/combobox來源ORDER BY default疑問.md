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
1.combobox DataSource來源為資料庫內表格,其中有一欄為數字用來決定item先後順序,其欄位為文字型態
2.combobox item呈現次序按照數字欄位去遞增
# Question:
1.發現有的項目排序在最前面
2.呈現結果並無照預期
# Answer:
1.**空字串**在文字順序權重比為最小
2.其數字欄位是**字串**型別，權重為1、10、11、2、3、4