# Metadata
Qty::10
Review::
Restructure::relation

### Think




# Exception

1. #flashcards 
- Highlight:typescript
- Question:將變數陣列傳入區域函數內做LINQ修改,此變數值不變
?
- Answer:發現只有push才能將值做異動

2. #flashcards 
- Highlight:C#
- Question:List 和 Array 分別為實值和參考型別差異在於
?
- Answer:其本身為參考型別,主要差異在元素為實值或參考

3. #flashcards 
- Highlight:javascript
- Question:psuh、shift、pop、unshift差異,pop無資料情況
?
- Answer:附加索引順序上,push常用理解就是附加在尾端,**unshift反之**，非直覺shift，pop無資料不會丟exception，像foreach一樣直接跳開


4. #flashcards 
- Highlight:C#
- Question:是否會跳錯
```
AddRange(LINQ操作後集合為空)
AddRange(null)
```
?
- Answer:LINQ操作集合就算為空也是個空集合物件不為null,不會exception

5. #flashcards 
- Highlight:python
- Question:DataFrame All arrays must be of the same length
?
- Answer:背後想像成表格結構，長度都需相同

6. #flashcards 
- Highlight:python
- Question:array 切片超過長度索引
?
- Answer:不exception

7. #flashcards 
- Highlight:python
- Question:DataFrame加入不合法矩陣
?
- Answer:不exception,會產出NaN類型

8. #flashcards 
- Highlight:python
- Question:遍歷字典跳出string indices must be integers
?
- Answer:把string 當成字典

9. #flashcards 
- Highlight:TypeScript
- Question:使用Map字典當指定相同key
?
- Answer:並不會丟exception只是會覆寫
```
this.dict.set('7','q26');// 7	其他    q26
this.dict.set('7','q26Remark');// 7	其他    q26
```

10. #flashcards 
- Highlight:html為動態讀取UI設定檔呈現
- Question:為何無將值填入UI
?
- Answer:發現model為字典型別，若無對應屬性去指定並不會異常
```
model[key] = value; //不存在key,不丟exception 
```
