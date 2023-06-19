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
3. NET CORE專案將2000多筆資料撈出來後透過前端ajax做分頁
4. 前後端分離串接前端連不上後端
5. 後端API專案在進行呼叫API測試
6. 在測試時後端刪除Action時簽章如下
```
ActionName ([FromBody] long sysSettingId)
```
7. 前後端分離專案前端發送request和後端API溝通時

# Question:
1. 404 找不到資源
2. 403.14 - Forbidden
3. 500
4. 同上
5. 401
6. 415 表示 "Unsupported Media Type"（不支援的媒體類型）
7. 衍生出400。The JSON value could not be converted to System.Int64. Path: $ | LineNumber: 0 | BytePositionInLine: 1.
8. CORS Prolicy
9. 405
# Answer:
1. 網址打錯，容易錯誤理解網址參數規範，下方呈現都是通用
```
url/qry
url?qry
```
2. 網址用預設網址,但是預設網頁被刪了
3. 此次發生原因為CORE ToList prase json ，ajax弄出分頁是筆數資料太多
4. 呼叫**後端協定**http、https造成異常
5. **權限**問題，檢查Controller或Action中將Authorize給移除即可
6. 檢查項目參考[[POSTMAN]]中Controller參數簽名設定
7. 檢查項目參考[[POSTMAN]]中Controller參數簽名設定[[API Prase JSON簽章和參數相關問題]]
8. 
- 前或後端本身有權限設定，但是後端Authorize將其移除，可能造成token失常
- 前端在進行呼叫時其應寫在ngOnInit而非constructor，可以想成winForm Form與Form_Load，要等建構子完成才能執行動作 
9. 方法不允許，錯誤HTTP方法，Controller為GET 呼叫用POST