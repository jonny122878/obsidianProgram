---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::9


#知識  #work 

# Unify
- 基本上錯誤碼可以歸類成造訪資源不存在、溝通基礎有問題(參數、協定、動詞)、權限遮蔽

1. #flashcards 
- Highlight:
- Question:404 找不到資源
?
- Answer:網址打錯，容易錯誤理解網址參數規範，下方呈現都是通用
```
url/qry
url?qry
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
- Answer:此次發生原因為CORE ToList prase json ，ajax弄出分頁是筆數資料太多

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
- Highlight:在測試時後端刪除Action時簽章如下
```
ActionName ([FromBody] long sysSettingId)
```
- Question:415 表示 "Unsupported Media Type"（不支援的媒體類型）
?
- Answer:前後端參數對應錯誤[[API Prase JSON簽章和參數exception]]

7. #flashcards 
- Highlight:前後端分離專案前端發送request和後端API溝通時
- Question:衍生出400。The JSON value could not be converted to System.Int64. Path: $ | LineNumber: 0 | BytePositionInLine: 1.
?
- Answer:前後端參數對應錯誤[[API Prase JSON簽章和參數exception]]


8. #flashcards 
- Highlight:操作[[POSTMAN]]進行後端測試
- Question:CORS Prolicy
?
- Answer:前或後端本身有權限設定，在做測試時移除Authorize，可能造成token失常

9. #flashcards 
- Highlight:新寫好前後端要進行串接
- Question:405
?
- Answer:方法不允許，錯誤HTTP方法，Controller為GET 呼叫用POST

10. #flashcards 
- Highlight:
- Question:
?
- Answer: