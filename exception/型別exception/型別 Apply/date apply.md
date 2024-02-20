2. #flashcards 
- Highlight:Oracle
- Question:如何寫入目前系統時間
?
- Answer:SYSDATE

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