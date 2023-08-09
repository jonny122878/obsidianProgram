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

#知識 
# Unify




1. #flashcards 
- Highlight:C#
- Question:
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
- Highlight:
- Question:
?
- Answer:

3. #flashcards 
- Highlight:
- Question:
?
- Answer: