# Metadata
Qty::
Review::
Restructure::

#work #資訊 
# Unify

## 本質

## 衍生衝突


- 參數是否允許NULL是要後端明確定義
- JSON字典和javascript字典格式稍微不同
- JSON日期本身為字串格式區分並無特別日期型態,因此後端接收日期變數也須用string接收
- class之間傳遞只允許為public

1. #flashcards 
- Highlight:POSTMAN模擬前端在傳送日期條件時，因頁面無設定條件因此將其value塞成null
- Question:"queryKey": "The queryKey field is required."
?
- Answer:檢查Controller函數簽名是否為DateTime?

2. #flashcards 
- Highlight:Web API專案串接
- Question:檢查明明是httpCode為正常，但後端接收時都無資料
?
- Answer:在傳遞class時，只能是public修飾子權限

3. #flashcards 
- Highlight:Controller return class copy Angular module.ts一份**一樣**類別名和屬性
- Question:console時發現後端傳入class有值，但調用其屬性就undefined
?
- Answer:在JSON中無區分**大小寫**，但其做協定溝通時會自行翻譯成小寫，因此Angular **module**要定義小寫

4. #flashcards 
- Highlight:
- Question:Error parsing column 8 (DATAUSESTATUSNAME=啟用 - String) 
?
- Answer:原因為C#欄位和JSON欄位型別並無對應，int、string去接收所導致

5. #flashcards 
- Highlight:載入頁面簽章時GET有二個參數，情境下有時是不會傳值
```
queryClauseScopeList(int ncProdPolicyClauseId,string goodsCode)
```
- Question:POSTMAN實際發送request時丟出400錯誤訊息
?
- Answer:若要讓此request成功，定義參數上需允許NULL
```
int?
```

6. #flashcards 
- Highlight:
- Question:直接將javascript內字典語法貼上後response error?
?
- Answer:JSON語法都需要加上雙引號
```
"Name":"add", 
```

7. #flashcards 
- Highlight:
- Question:串接API 在後端return "ExceptionMessage": "找到多個符合下列要求的動作?
?
- Answer:訊息直覺:Controller參數預設型態宣告不能再宣告同樣，
```
[FormBody] class
```

8. #flashcards 
- Highlight:
- Question:串接API return "Message": "此資源不支援要求實體的媒體類型 'application/javascript'。"?
?
- Answer:Controller參數預設型態串接不符，class = json

9. #flashcards 
- Highlight:因條件只有二參數有值，因此語法如下
```
        let queryId = <CommonQueryModel>{
            prodPolicyClauseId: this.queryKey.ncProdPolicyClauseId,
            prodPolicyClauseScopeMId: data.ncProdPolicyScopeID,          
        };
```
- Question:為何丟出400參數無法綁定
?
- Answer:不能將直覺用C#去類推，其必須每個屬性都需指定值，沒有指定不會**默認指定null**

10. #flashcards 
- Highlight:Angular中調用Contoller API
- Question:檢查Angular中service函數名和參數都為有對應，為何固定return 0
?
- Answer:遺漏**FromBody**

14. #flashcards 
- Highlight:
- Question:
?
- Answer:

15. #flashcards 
- Highlight:
- Question:
?
- Answer:

16. #flashcards 
- Highlight:
- Question:
?
- Answer:

6. #flashcards 
- Highlight:在測試時後端刪除Action時簽章如下
```
ActionName ([FromBody] long sysSettingId)
```
- Question:415 表示 "Unsupported Media Type"（不支援的媒體類型）
?
- Answer:前後端參數對應錯誤[[API JSON 400 415 exception]]


7. #flashcards 
- Highlight:前後端分離專案前端發送request和後端API溝通時
- Question:衍生出400。The JSON value could not be converted to System.Int64. Path: $ | LineNumber: 0 | BytePositionInLine: 1.
?
- Answer:前後端參數對應錯誤[[API JSON 400 415 exception]]


10. #flashcards 
- Highlight:Angular
- Question:POST API參數為字串,明明POSTMAN無異常,但用Angular呈現415
?
- Answer:若POST string預設為text-plain,需要將string自行轉成JSON後再POST

11. #flashcards 
- Highlight:
- Question:用POSTMAN呼叫C#開發API專案,但明明參數都對還是呈現415
?
- Answer:檢查content-type類型,C#只接受JSON
https://blog.miniasp.com/post/2019/01/20/Angular-HttpClient-Pitfall-and-Tricks
