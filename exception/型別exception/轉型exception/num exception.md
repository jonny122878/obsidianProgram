# Metadata
Qty::2
Review::
Restructure::relation 1~2

### Think

# Exception


6. #flashcards 
- Highlight:typescript
- Question:丟出Infinity
?
- Answer:1/0數學上無意義

2. #flashcards 
- Highlight:typescript
- Question:畫面上百分比數字必須 * 100 呈現，但發現會有偽差
```
4.44 * 100 = 444.00000000000006
```
?
- Answer:目前發現有些數字運算才有此情況，解決方式捨去幾位
```
let value = Number(input) * 100;
//捨去只到小數位後第4位
let skip = value.toFixed(4);
//將其捨棄小數後為0
let result = Number(Number(skip).toString());

3.1 用此方法也會是小數一位
```

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