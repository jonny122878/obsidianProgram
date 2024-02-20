# Metadata
Qty::6
Review::
Restructure::relation

### Think

# Exception


1. #flashcards 
- Highlight:表格中表格列為表單，click新增鈕會新增表格列
- Question:丟出Cannot find control with path: '0 -> isMaster'
?
- Answer:其意思類似陣列索引超出界限，檢查後為html、component無綁定formArrayName造成，名稱要一致，且html中要放在迴圈外載入
ts:
```
      this.detailForm = new FormGroup({
          'List': new FormArray([]),
      });
```
html:
```
<div formArrayName="List">
<div *ngFor="let item of this.form.get('List')['controls']; let j=index" [formGroupName]="j">
```

2. #flashcards 
- Highlight:表單維護有個子表單參數表格維護，可透過新增鈕增加表格列
ts:
```
//原始對應結構
    model: ProdClauseDescDetailFormModel = <ProdClauseDescDetailFormModel>{  paramList: [] };
//FormGroup初始設定，調用ngOnInit
private initFormGroup() {
this.detailForm = new FormGroup({
'prodPolicyClauseId': new FormControl(this.detailData.prodPolicyClauseId),
'paramsList': new FormArray([]),
});}
//寫在新增表格列函數
this.model.paramList.push(<ParamsModel>{});
        let formGroup = new FormGroup({
'prodPolicyClauseId': new FormControl(this.detailForm.controls["prodPolicyClauseId"].value),
});        (<FormArray>this.detailForm.controls["paramsList"])).push(formGroup);
//從後端讀取表格
let arr = data.data as ParamsModel[];
arr.forEach(item =>
{
	this.model.paramList.push(<ParamsModel>
	{                        prodPolicyClauseId:item.prodPolicyClauseId,

});

let formGroup = new FormGroup({
'prodPolicyClauseId': new FormControl(item.prodPolicyClauseId),
});
(<FormArray>(this.detailForm.controls["paramsList"])).push(formGroup);     this.detailForm.controls['paramsList'].setValue(this.model.paramList);   
```
- Question:為何編輯在完重新載入時發現原本列表疊加上去，ex:本來是表格4列，存檔後變成8列
?
- Answer:原因為component內FormArray無清空，類似**參考**型別概念要清除源頭
```
this.model.paramList.length = 0; //ok
(<FormArray>(this.detailForm.controls["paramsList"])).clear(); //error
```

3. #flashcards 
- Highlight:前端表格為FormArray呈現
- Question:ngModel cannot be used to register form controls with a parent formGroupName or formArrayName directive
?
- Answer:設定屬性讓其不受表單規則規範
```
[ngModelOptions]="{standalone: true}"
```

4. #flashcards 
- Highlight:ngModel綁定元件
- Question:If ngModel is used within a form tag, either the name attribute must be set or the form  control must be defined as 'standalone' in ngModelOptions.
?
- Answer:html input name屬性沒設定,且若為ngFor展開name屬性不重複

5. #flashcards 
- Highlight:
- Question:html formArrayName動態展開，html綁定無效
```
[disabled]="!canEdit"
```

?
- Answer:必須在component
```
this.detailForm.get('rateList').disable();
```

6. #flashcards 
- Highlight:
- Question:直接將若型別轉成FormArray,但發現無法調用集合相關函數
```
arr.controls.map(r => r).map(r => r)
```
?
- Answer:其非[],為物件型陣列,要調用屬性
```
let results = arr.controls.map(r =>
{
	let f = r as FormGroup;
	return f.controls['sharePrem'].value;
});
```
