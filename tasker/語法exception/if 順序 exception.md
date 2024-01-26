# Metadata
Qty::3
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突


# Exception


1. #flashcards 
- Highlight:衍生上述情境，用字串來接收combobox選取值
```
if(this.selectValue === '')
```
- Question:為何防呆無法條件無法成立
?
- Answer:同上若string無實體化default undefined
```
if(this.selectValue === undefined)
```

2. #flashcards 
- Highlight:python
- Question:為何單元測試明明跑錯都無錯誤訊息
```
try:
    assert
except Exception as e:
except AssertionError:
```
?
- Answer:exception有分嚴謹和寬鬆

3. #flashcards 
- Highlight:C#，excel字串用replace函數替換對應名目尺度(ex:條件式取代字串:sample:31-十一月-2018)
- Question:取代出只符合一半情況
?
- Answer:
  - 條件式的守則是從**嚴謹到寬鬆**，不然就會有擋下來沒有達到預期的效果，順序搭配鬆緊非常重要，就是成敗的關鍵。
  - 可是你如果從一月取代到十二月時就會出錯，因為一月會先把十一月的後二字給取代掉，從而導致無法預期的結果。

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