---
data:2023-03-14
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:PROCEDUCE


# Highlight:
1. PROCEDUCE移轉到MTB01單位是以批覆書,但單張披覆書對應法人會有多個**1-M**關係,因此透過CURSOR+UPDATE方式將欄位串接
ex:法人1+法人2....
2. INSERT SQL用 'result' 寫到varbinary(max)丟出不允許資料類型varchar隱含轉到varbinary(max),請使用CONVET function
3. INSERT INTO SQL下丟出**字串或二進位會被截斷**
4. PROCEDUCE進行將計算結果寫入時出現**資料庫定序**問題
7.在CASE WHEN對二個指定欄位做判別時若為二者空白與NULL均為一種情況，最後將呈現結果將二個欄位給相加
```
CASE ISNULL(,'') + ISNULL(,'') THEN 'Y'
ELSE 'N'
```
8. Oracle中日期型態
# Question:
1. 轉出來結果有些欄位明明是對應法人,但其產出NULL
2. 應都是string型態,為何丟出如上訊息
3. 肉眼上看文本算字數是沒有超過的
4. 何謂資料庫定序?
5. 資料類型ntext不可用UNION、INTERSECT 或EXCEPT運算子的運算元，因為不相容
6. 在INSERT中文字時，會因為特殊字元而造成亂碼情況
8. Oracle中進行WHERE述句條件日期型別比較該如何處理
# Answer:
1. 發先原因再於1張批覆書對應3個法人,但是其中**1位法人NULL**,任何型態+NULL=NULL
2.varbinary本質已經**跳脫** char、nchar、varchar、nvarchar這些規則,可以想成是另種類似string型態了
3.很明顯欄位**長度不足**,下方為各種型別儲存容量
- char、varchar(**2**) 中字只能塞一個,英字可以塞二個
- nchar、nvarchar(**2**) 中英都能塞二個
- **換行符號**會佔2字元
4.varchar => nvarcahar，不同字串型態不會**自動轉型**
5.'型別規範問題**text**只拿來記錄,若要運算nvarcahar(max)可解決
6.在insert值前面加入N修飾子即可
7.在欄位做串接Aggregate時，忽略default 符號中間串接符號，導致異常
8. 其自身並無MS-SQL一樣默認語法轉型，因此必須要特別將日期型別轉成字串來處理
```
and '2023-01-01' <= TO_CHAR(a.EXP_DATE,'YYYY-MM-DD') 
```