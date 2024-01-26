# Metadata
Qty::7
Review::
Restructure::relation

### Think



## 本質
- 抽象對應結構體日期、時間
- 用字串格式表示日期
- 轉型日期函數
- 轉型日期函數各顆粒度
- 轉型日期函數擴充方法
## 衍生衝突
- TimeSpan 2
- JSON 5
- excel日期和各種類似日期
- getMonth 理解不同

# Exception

1. #flashcards 
- Highlight:C#
- Question:能吃幾種日期格式
?
- Answer:
```
using System.Globalization;
日期數字10碼/和-:
var input = "2022-04-15";
var input = "2022/04/15";
var result = Convert.ToDateTime(input, new CultureInfo("en-US"));
日期數字8碼:
var input = "20220415";
var dateFormatArr = new string[] { "yyyy/MM/dd", "yyyy-MM-dd", "yyyyMMdd"};
var result = DateTime.ParseExact(input, dateFormatArr ,CultureInfo.InvariantCulture,DateTimeStyles.AllowWhiteSpaces);
日期中文excel格式:
var result = Convert.ToDateTime(input, new CultureInfo("zh-TW"));
var input = "14-四月-2022";
```

2. #flashcards 
- Highlight:C#
- Question:TimeSpan型別不能用.ToString("yyyy-MM-dd HH:mm:ss")
?
- Answer:其為時間抽象，只能調用ToString() => HH:mm:ss...毫秒

3. #flashcards 
- Highlight:typescript、javascript
- Question:日期轉字串能否透過ToString()之類格式化
?
- Answer:只能透過組字串方式
```
const currentDate = new Date();
const year = currentDate.getFullYear();
const month = (currentDate.getMonth() + 1).toString().padStart(2, '0'); // +1 是因為月份從0開始，padStart用於填充0，使月份成為兩位數
const day = currentDate.getDate().toString().padStart(2, '0');
const nowDate = `${year}-${month}-${day}`;
```

4. #flashcards 
- Highlight:typescript、javascript
- Question:獲取當前月份，用getMonth但是其得到值為當前月份-1
?
- Answer:其內部邏輯為**array**，因此索引從0開始計數

5. #flashcards 
- Highlight:查詢˙條件日期只需要查到Date非DateTime型態
- Question:"expDate": "2023-05-23T", error
?
- Answer:
 - Date型別:"expDate": "2023-05-23" 
 - DateTime型別:"expDate": "2023-05-23T:00.00.000Z"

6. #flashcards 
- Highlight:前後端專案條件查詢
- Question:使用者條件只需到年月日，後面分秒該如何移除來確保比較基準為正常
?
- Answer:可用Prase先去轉型後會自動default:上午12:00:00
```
DateTime.Prase(date.ToString("yyyy/MM/dd"))
```
衍生日期型別概念，JSON並無特定日期型別，其為字串型別並透過**字串格式**來區分，因此推論C# 接收日期欄位必須為**string**而不是DateTime


7. #flashcards 
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

8. #flashcards 
- Highlight:
- Question:
?
- Answer: