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
原始系統行將textbox and calendar封裝成一個日期文字框元件,但是發現一個元件缺陷,user可透過**文字框自行輸入**,不透過click textbox彈出calendar去設定日期
# Question:
為了讓txt元件不能修改,css設定**disabled**,但是發現PostBack後原本txt值並沒有保留
# Answer:
因[[ASP.NET機制]]會將disabled自動轉譯成不能輸入,因此不會保留值,要用**readonly**
[can't get value from readonly or disabled textbox control asp.net](https://stackoverflow.com/questions/10227003/cant-get-value-from-readonly-or-disabled-textbox-control-asp-net)



