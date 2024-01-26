# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::9
Review::


#資訊    #work 

# Unify
- html模塊若**通信key名稱**不同不丟任何錯誤，依循SRP準則
- JSON字典類似匿名型別**動態生成**不會檢查錯誤
- 條件式若符合語法不會檢查錯誤
- 字典透過陣列值指定值不會檢查

1. #flashcards
- Highlight:子html列表顯示條件為其他子html內combobox值決定
- Question:並沒有按照條件做顯示與否
?
- Ans:FormGroup名稱無對應
```
//子html
<normal-commission-list #normalcomiList 
[ngClass]="{'hidden': comiRateSettingDetail.detailForm.value.commissionType != 1 }">
//子component
'contextType': new FormControl(this.detailData.contextType, [Validators.required]),
```



3. #flashcards 
- Highlight將原本結構轉換成類似C匿名型別字典後，進行調用
- Question:調用字典內不存在屬性為何無丟錯
?
- Answer:字典語法錯誤，javascript特性無丟exception
```
map ....
{address:r,scope:c.scopeList[0]}
let address = r.address.locationName;
```

4. #flashcards 
- Highlight:
- Question:雙迴圈外層迴圈計數變量指定array撈出結果並不符合
?
- Answer:迴圈計數變量作用域不包含內層，與直覺有差異
```
group.forEach((r,i) => {
            //用array索引將表單與表格資料填入
            r.forEach(c => {
                let form = this.getFormList.at(c) as FormGroup;
                console.log(i); //undefined
```

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
- Highlight:TypeScript
- Question:使用Map字典當指定相同key
?
- Answer:並不會丟exception只是會覆寫
```
this.dict.set('7','q26');// 7	其他    q26
this.dict.set('7','q26Remark');// 7	其他    q26
```

7. #flashcards 
- Highlight:
- Question:點擊新增按鈕明明formArray有增加，但html無效果
?
- Answer:發現tr標籤移除model，但html並無移除
```
*ngIf="item.value.isEdit"
```

8. #flashcards 
- Highlight:html為動態讀取UI設定檔呈現
- Question:為何無將值填入UI
?
- Answer:發現model為字典型別，若無對應屬性去指定並不會異常
```
model[key] = value; //不存在key,不丟exception 
```

9. #flashcards 
- Highlight:python
- Question:明明assert有異常,為何無拋exception
?
- Answer:中間區塊多換行無運行導致
```
	line1
		line2
	line1
```


10. #flashcards 
- Highlight:
- Question:
?
- Answer: