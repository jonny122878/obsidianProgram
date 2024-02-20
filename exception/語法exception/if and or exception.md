# Metadata
Qty::1
Review::
Restructure::relation 1

### Think

# Exception


1. #flashcards 
- Highlight:檢核欄位數值必須等於0或是null
- Question:
```
var isPremNull = !(sp.PremShare.HasValue);
var isPremZero = (sp.PremShare.HasValue && sp.PremShare.Value == 0);
//不是0和null
if (!(isPremZero || !isPremNull)) 
{

}
```
?
- Answer:邏輯條件是樹狀先後順序要先整出
```
有值 => 0
	=> 任意數
無值
```

```
var isPremZero = (sp.PremShare.HasValue && sp.PremShare.Value == 0);
//不是0和null
if (!isPremZero && sp.PremShare.HasValue) 
{

}
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

4. #flashcards 
- Highlight:
- Question:
?
- Answer:

5. #flashcards 
- Highlight:
- Question:
?
- Answer: