# Metadata
Qty::6
Review::
Restructure::relation

### Think



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
- Question:迴圈計數變量指定array撈出結果並不符合
?
- Answer:迴圈內無宣告變量也不會提示錯誤
```
r.forEach(c => {
	let innerScopeList: ObjectScopeList[] = this.scopeList[i];
```

6. #flashcards 
- Highlight:python
- Question:明明assert有異常,為何無拋exception
?
- Answer:中間區塊多換行無運行導致
```
	line1
		line2
	line1
```
