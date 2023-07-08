---
date:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:金財通
Author:
Note Type:
Topics:
#資訊 

# Unify

1. #flashcards 
- Highlight:POSTMAN模擬前端在傳送日期條件時，因頁面無設定條件因此將其value塞成null
- Question:"queryKey": "The queryKey field is required."
?
- Answer:檢查Controller函數簽名是否為DateTime?

2. #flashcards 
- Highlight:查詢˙條件日期只需要查到Date非DateTime型態
- Question:"expDate": "2023-05-23T", error
?
- Answer:
 - Date型別:"expDate": "2023-05-23" 
 - DateTime型別:"expDate": "2023-05-23T:00.00.000Z"

3. #flashcards 
- Highlight:Web API專案串接
- Question:檢查明明是httpCode為正常，但後端接收時都無資料
?
- Answer:在傳遞class時，只能是public修飾子權限

4. #flashcards 
- Highlight:前後端專案條件查詢
- Question:使用者條件只需到年月日，後面分秒該如何移除來確保比較基準為正常
?
- Answer:可用Prase先去轉型後會自動default:上午12:00:00
```
DateTime.Prase(date.ToString("yyyy/MM/dd"))
```
衍生日期型別概念，JSON並無特定日期型別，其為字串型別並透過**字串格式**來區分，因此推論C# 接收日期欄位必須為**string**而不是DateTime

5. #flashcards 
- Highlight:首頁查詢條件
- Question:前端查詢元件不指定任何條件，其return 400 code
?
- Answer:確認後端型別是否都有設定NULL機制，string、int....，

6. #flashcards 
- Highlight:Controller return class copy Angular module.ts一份**一樣**類別名和屬性
- Question:console時發現後端傳入class有值，但調用其屬性就undefined
?
- Answer:在JSON中無區分**大小寫**，但其做協定溝通時會自行翻譯成小寫，因此Angular **module**要定義小寫

7. #flashcards 
- Highlight:
- Question:Error parsing column 8 (DATAUSESTATUSNAME=啟用 - String) 
?
- Answer:原因為C#欄位和JSON欄位型別並無對應，int、string去接收所導致

8. #flashcards 
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

9. #flashcards 
- Highlight:
- Question:直接將javascript內字典語法貼上後response error?
?
- Answer:JSON語法都需要加上雙引號
```
"Name":"add", 
```

10. #flashcards 
- Highlight:
- Question:串接API 在後端return "ExceptionMessage": "找到多個符合下列要求的動作?
?
- Answer:訊息直覺:Controller參數預設型態宣告不能再宣告同樣，
```
[FormBody] class
```

11. #flashcards 
- Highlight:
- Question:串接API return "Message": "此資源不支援要求實體的媒體類型 'application/javascript'。"?
?
- Answer:Controller參數預設型態串接不符，class = json

12. #flashcards 
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

13. #flashcards 
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