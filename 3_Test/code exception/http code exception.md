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
4. 後端API專案在進行呼叫API測試
5. 在測試時後端刪除Action時簽章如下
```
ActionName ([FromBody] long sysSettingId)
```
7. 前後端分離專案前端發送request和後端API溝通時
# Question:
1. 404 找不到資源
2. 403.14 - Forbidden
3. 500 流量太大
4. 401
5. 415 表示 "Unsupported Media Type"（不支援的媒體類型）
6. 衍生出400。The JSON value could not be converted to System.Int64. Path: $ | LineNumber: 0 | BytePositionInLine: 1.
7. CORS Prolicy
8. 400
# Answer:
1.網址打錯，容易錯誤理解網址參數規範，下方呈現都是通用
```
url/qry
url?qry
```
2.網址用預設網址,但是預設網頁被刪了
3.此次發生原因為CORE ToList prase json ，ajax弄出分頁是筆數資料太多
4. 通權限問題，檢查Controller或Action中將Authorize給移除即可
5. 檢查項目參考[[POSTMAN]]中Controller參數簽名設定
6. 檢查項目參考[[POSTMAN]]中Controller參數簽名設定
7. 
- 前或後端本身有權限設定，但是後端Authorize將其移除，可能造成token失常
- 前端在進行呼叫時其應寫在ngOnInit而非constructor，可以想成winForm Form與Form_Load，要等建構子完成才能執行動作 
8. 通常都為發送和接收端欄位無對應所造成[[API Prase JSON簽章和參數相關問題]]
9. 