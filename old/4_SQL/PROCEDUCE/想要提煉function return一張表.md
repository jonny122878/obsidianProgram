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
Topics:


# Highlight:
目前排程每日會透過PROCEDUCE將資料移轉,但隨著時間推移資料量越來越大,user希望能否只保留當月份,之前資料只保留月底最後一日即可
# Question:
所有透過PROCEDUCE透過排程每日計算出來結果表都符合此規則,因此想封裝副程式,直覺想到PROCEDUCE、Function、exec SELECT語法再用FROM去接收
# Answer:
PROCEDUCE本身定位可想成是計算函數,因此return int的只是負責呈現**計算結果狀態**
exec本身內建PROCEDUCE也帶有同樣特性,function因其特性不能再調用PROCEDUCE,但需求是SELECT語法要組成字串丟入exec也沒辦法
解決方法改成用暫存表,資料連線斷開就隨之消失




