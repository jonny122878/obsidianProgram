# Metadata
Qty::7
Review::
Restructure::

### Think



# Exception



1. #flashcards 
- Highlight:C#
- Question:?.First  
?
- Answer:Sequence contains no elements

2. #flashcards 
- Highlight:C#
- Question:FirstOrDefault 是否會有延遲特性
?
- Answer:單一元素不會延遲

3. #flashcards 
- Highlight:javascript
- Question:如何將IEnumerable轉成array
?
- Answer:ToArray: Array.prototype.slice.call(**IEnumerable**) 

4. #flashcards 
- Highlight:javascript
- Question:直覺用Select(r => r.Value)取不到整個集合?
```
IEnumerable<KeyValuePair<int, List<BookLendRecord>>>
        let records = lendLists.filter(object => {
            return object.Key == new Number(id);
        }).map(r => r.Value)[0];
```
?
- Answer:直覺錯誤map預設回傳**集合**，所以是包在集合中元素內

5. #flashcards 
- Highlight:jQuery
- Question:在做展開時能否透過LINQ思維調用
?
- Answer:
- jQuery類LINQ本身就帶有**防Null**
- jQuery類LINQ default extension **ToArray**

6. #flashcards 
- Highlight:python
- Question:'map' object is not subscriptable array 
?
- Answer:用map之後類似IEnumerable結構,並沒有辦法直接用array調用
```
result[0]
```

7. #flashcards 
- Highlight:LINQ,在調用自訂義RowCommand時其為一組string[]，將其
```
arr.Select(r => r[0])
```
- Question:產出結果很奇怪都為**數字**
?
- Answer:因為當在做單一string時會自動理解成
```
IEnumerable<char>
```
因此產出原本產出數字結果為字元

