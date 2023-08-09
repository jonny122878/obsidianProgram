---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::9

#知識 #work 
# Unify
- 檢查html、component雙向綁定是否都有對應到
- label不屬於FormControl
- combobox change event和一般理解js不一樣


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
- Highlight:DropDownList需放一個default請選擇選項
- Question:衍生上述情境另個頁面ts按照相同model但確無法綁定
?
- Answer:
  - 檢查ts內是否有在**FormGroup**註冊
  - 檢查html內是否在**formControlName**註冊，才能將FormGroup綁起來

3. #flashcards 
- Highlight:編輯狀態表單頁面載入表單填值
- Question:訊息:component.ts:232 ERROR Error: NG01002: Must supply a value for form control with name: 'paramType'，類似[[js語法]]特性後面指令無法正確執行
?
- Answer:若已經有用FormGroup後，**所有**key-value都要設定，其才會識別為相同型別
```
this.detailForm.setValue({
  'prodPolicyClauseId': this.detailData.prodPolicyClauseId || 0,
  });
```


4. #flashcards 
- Highlight:編輯狀態表單頁面載入表單填值
- Question:檢查html中formControlName 、ts中FormGroup 都有名稱對應，Debug console也無錯誤訊息，但是表單無法將值給綁定
?
- Answer:檢查html中form標籤是否有設定
```
<form class="form-horizontal" [formGroup]="form">
form: FormGroup;
```

5. #flashcards 
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

6. #flashcards 
- Highlight:將label元件綁定到FormControl上
```
<label class="col-md-7" formControlName="lbAddress2">地址</label>
```
- Question:No value accessor for form control name: 'lbAddress1'
?
- Answer:FormControl只能適用input型標籤元件

7. #flashcards 
- Highlight:combobox change to set label，combobox and label是可動態新增
- Question:原本思路為ngFor將label id做計數，但發現html文件 label id無法累加
?
- Answer:解決問題思路要用**綁定**方式，而不是傳統jQuery時代透過DOM操作，直接透過插值語法綁定函數計算即可
```
<label class="col-md-7">{{getlbAddress(j)}}</label>

```


8. #flashcards 
- Highlight:前端表格為FormArray呈現
- Question:ngModel cannot be used to register form controls with a parent formGroupName or formArrayName directive
?
- Answer:設定屬性讓其不受表單規則規範
```
[ngModelOptions]="{standalone: true}"
```

9. #flashcards 
- Highlight:combobox change前面防呆方法檢查目前FormGroup
- Question:是否有類似preventDefault 方法調用?
?
- Answer:preventDefault() 方法通常在需要阻止事件的預設行為時使用，例如在點擊事件中防止超連結的跳轉或按鈕的提交等。對於 change 事件來說，它並沒有一個通用的預設行為需要阻止，因此不需要使用 preventDefault() 方法。無內建preventDefault因此遍歷FormGroup，特別注意當選取combobox當下此資料就已經寫到FormGroup內
```
let selectRepeat = 0;
for(var i=0;i<this.getFormList.length;i++)
        {
            let form = this.getFormList.at(i) as FormGroup;
            if(form.controls["address"].value == valAddress &&
               form.controls["scope"].value == valScope)
            {
                selectRepeat = selectRepeat + 1;
            }
        }
```



13. #flashcards 
- Highlight:
- Question:
?
- Answer:
