# Metadata
Qty::6
Review::
Restructure::

### Think





# Exception


1. #flashcards 
- Highlight:C#
- Question:TimeSpan型別不能用.ToString("yyyy-MM-dd HH:mm:ss")
?
- Answer:其為時間抽象，只能調用ToString() => HH:mm:ss...毫秒

2. #flashcards 
- Highlight:typescript、javascript
- Question:獲取當前月份，用getMonth但是其得到值為當前月份-1
?
- Answer:其內部邏輯為**array**，因此索引從0開始計數

3. #flashcards 
- Highlight:查詢˙條件日期只需要查到Date非DateTime型態
- Question:"expDate": "2023-05-23T", error
?
- Answer:
 - Date型別:"expDate": "2023-05-23" 
 - DateTime型別:"expDate": "2023-05-23T:00.00.000Z"

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
- Highlight:typescript
- Question:如何進行有效日期檢查
?
- Answer:Date.parse('')可進行日期格式return NaN,要小心會吃民國年 年月..等等格式
並且其允許2023/02/30這種
```
2023
110/11
```
比較好方法用Regex搭配檢查日期月份和日

6. #flashcards 
- Highlight:C#
- Question:DateTime.Prase能否吃民國年
?
- Answer:
```
2023/11/20 ok
2023/2/11 ok
113/03/11 error轉成功,但是是西元113年
```