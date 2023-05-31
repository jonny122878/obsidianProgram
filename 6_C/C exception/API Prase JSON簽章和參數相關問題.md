---
data:
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


# Highlight:
1. POSTMAN模擬前端在傳送日期條件時，因頁面無設定條件因此將其value塞成null
2. 衍生上述情境，其日期只需要查到Date非DateTime型態
5. 前端查詢元件不指定任何條件，其return 400 code
8. 載入頁面簽章時GET有二個參數，情境下有時是不會傳值
```
queryClauseScopeList(int? ncProdPolicyClauseId,string? goodsCode)
```
# Question:
1. "queryKey": "The queryKey field is required."
2. "expDate": "2023-05-23T", error
3. 檢查明明是httpCode為正常，但接收時都無資料
4. 使用者條件只需到年月日，後面時分秒該如何移除來確保比較基準為正常
5. 前端查詢元件不指定任何條件，其return 400 code
6. 同上查此異常發現Angular發送class和C#接收class其欄位名稱一致，但大小寫**不同**，是否有影響?
7. Error parsing column 8 (DATAUSESTATUSNAME=啟用 - String) 
8. POSTMAN實際發送request時丟出400錯誤訊息
9. 直接將js內字典語法貼上後response error?
10. 串接API 在後端return "ExceptionMessage": "找到多個符合下列要求的動作?
11. 串接API return "Message": "此資源不支援要求實體的媒體類型 'application/javascript'。"?
  
 

  
# Answer:
1. 檢查Controller函數簽名是否為DateTime?
2. 
- Date型別:"expDate": "2023-05-23" 
- DateTime型別:"expDate": "2023-05-23T:00.00.000Z"
3. 在傳遞class時，只能是public修飾子權限
4. 可用Prase先去轉型後會自動default:上午12:00:00
```
DateTime.Prase(date.ToString("yyyy/MM/dd"))
```
衍生日期型別概念，JSON並無特定日期型別，其為字串型別並透過**字串格式**來區分，因此推論C# 接收日期欄位必須為**string**而不是DateTime
5. 確認後端型別是否都有設定NULL機制，string、int....，
6. 在JSON中無區分**大小寫**
7. 原因為C#欄位和JSON欄位型別並無對應，int、string去接收所導致
8. 若要讓此request成功，定義參數上需允許NULL
```
int?
```
9. JSON語法都需要加上雙引號
```
"Name":"add", 
```
10. 訊息直覺:Controller參數預設型態宣告不能再宣告同樣，ex:[FormBody] class
11. Controller參數預設型態串接不符，class = json

