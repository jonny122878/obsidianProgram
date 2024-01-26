# Metadata
Qty::4
Review::
Restructure::relation、unify

### Think
# Unify

## 本質

## 衍生衝突


# Exception


1. #flashcards 
- Highlight:typescript
- Question:在接收值時有let、const、var如何選擇?
?
- Answer:let、const像C#一樣原理作用域，var小心使用上會有弱型別特有**hoisting**


2. #flashcards 
- Highlight:typescript
- Question:為何sum無法累加且IDE會丟紅字
```
        let sum:number = 0;
            quotas.forEach(r => 
                {
                    sum = sum + r;
                });
```
?
- Answer:作用域理解有問題，foreach內有點類似函式無副作用

3. #flashcards 
- Highlight:javascript

- Question:操作DOM為何無作用?
?
- Answer:
  - script本身也是有作用域概念，操作的DOM要放前面表示有宣告能操作
  ```
  <body>
  DOM.....  
  </body>
  <script></script>
  ```
  - script放置位置結論:
  - 放在head內為所需**副程式** ex:jQuery
  - 放置在body後為**操作DOM**且**不用event**

4. #flashcards 
- Highlight:python
- Question:import套件一直執行內部程式
?
- Answer:引入時將結構和調用code用 if main給隔離

5. #flashcards 
- Highlight:
- Question:
?
- Answer: