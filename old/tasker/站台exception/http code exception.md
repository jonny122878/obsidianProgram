# Metadata
Qty::8
Review::
Restructure::

#work #資訊 
# Unify

## 本質

## 衍生衝突

- 造訪資源不存在，以及衍生情境預設跳轉頁不存在 404、403.14
- 雙方溝通參數有問題、衍生參數型別 400 415
- 雙方溝通協定有問題、衍生動詞不對 500 405
- 權限遮蔽 401

1. #flashcards 
- Highlight:
- Question:404 找不到資源
?
- Answer:網址打錯，容易錯誤理解網址參數規範，下方呈現都是通用
```
url/qry
url?qry
```
若正常直覺打還是Controller/Action注意Controller設定
```
[Route("[controller]")]
```

2. #flashcards 
- Highlight:部署早點下班載入時跳出訊息
- Question:403.14 - Forbidden
?
- Answer:網址用預設網址,但是預設網頁被刪了

3. #flashcards 
- Highlight:NET CORE專案將2000多筆資料撈出來後透過前端ajax做分頁
- Question:500
?
- Answer:站台異常若不特別try catch就會返回此代碼，ajax弄出分頁是筆數資料太多

4. #flashcards 
- Highlight:前後端分離串接前端連不上後端
- Question:500
?
- Answer:呼叫**前後端協定一致**http、https造成異常

5. #flashcards 
- Highlight:後端API專案在進行呼叫API測試
- Question:401
?
- Answer:**權限**問題，檢查Controller或Action中將Authorize給移除即可

6. #flashcards 
- Highlight:操作[[POSTMAN]]進行後端測試
- Question:CORS Prolicy
?
- Answer:前或後端本身有權限設定，在做測試時移除Authorize，可能造成token失常

7. #flashcards 
- Highlight:新寫好前後端要進行串接
- Question:405
?
- Answer:方法不允許，錯誤HTTP方法，Controller為GET 呼叫用POST

8. #flashcards 
- Highlight:C#
- Question:站台若丟出exception,能否繼續執行
?
- Answer:一樣可test