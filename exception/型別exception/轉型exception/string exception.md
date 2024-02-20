# Metadata
Qty::1
Review::
Restructure::

### Think

# Exception

1. #flashcards 
- Highlight:C#
- Question:字串轉其他字元
?
- Answer:
  - 中字UTF8:byte佔3個
  - 中字ANSI:byte佔2個
```
string str = "test對";
var bytes = Encoding.UTF8.GetBytes(str);
var charArr = Encoding.UTF8.GetChars(bytes);
var encode = Convert.ToInt32(charArr[4]);
```


