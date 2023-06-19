---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:金財通
Author:
Note Type:
Topics:
#資訊 

# Highlight:
1. DropDownList需放一個default請選擇選項
2. 同上
3. Angular本身可以設定**AOP屬性**來達到表單防呆效果，ex:C# Model設定
html:
```
<button type="button" class="btn btn-primary" (click)="save()" [disabled]="detailForm.invalid">
            <i class=" fa fa-search"></i> 儲存
</button>
```
component.ts:
```
ngOnInit(): void {
	this.detailData = <ProdClauseDetailFormModel>{};
	this.detailForm = new FormGroup({
	'version': new FormControl(this.detailData.version, [Validators.required]),
});

```
4. 首頁表格點擊編輯按鈕時進行表單填值
5. 同上
7. 表單維護有個子表單參數表格維護，可透過新增鈕增加表格列
ts:
```
//原始對應結構
    model: ProdClauseDescDetailFormModel = <ProdClauseDescDetailFormModel>{  paramList: [] };
//FormGroup初始設定，調用ngOnInit
    private initFormGroup() {
        this.detailForm = new FormGroup({
            'prodPolicyClauseId': new FormControl(this.detailData.prodPolicyClauseId),
            'clauseCode': new FormControl(this.detailData.clauseCode),
            'clauseDesc': new FormControl(this.detailData.clauseDesc, [Validators.required]),
            'clauseDescEng': new FormControl(this.detailData.clauseDescEng, [Validators.required]),
            'paramsList': new FormArray([]),
        });
}
//寫在新增表格列函數
this.model.paramList.push(<ParamsModel>{});
        let formGroup = new FormGroup({
            'prodPolicyClauseId': new FormControl(this.detailForm.controls["prodPolicyClauseId"].value),
            'prodPolicyClauseParamId': new FormControl(),
            'clientShowName': new FormControl(),
            'paramCode': new FormControl(col2Val),
            'paramType': new FormControl(this.paramType2s),
        });
        (<FormArray>(this.detailForm.controls["paramsList"])).push(formGroup);
//從後端讀取表格
let arr = data.data as ParamsModel[];
arr.forEach(item =>
{
	this.model.paramList.push(<ParamsModel>
	{                        prodPolicyClauseId:item.prodPolicyClauseId,
	prodPolicyClauseParamId:item.prodPolicyClauseParamId,
paramCode:item.paramCode,
paramType:item.paramType,                        clientShowName:item.clientShowName
});

let formGroup = new FormGroup({
                    'prodPolicyClauseId': new FormControl(item.prodPolicyClauseId),
                    'prodPolicyClauseParamId': new FormControl(item.prodPolicyClauseParamId),
                    'clientShowName': new FormControl(item.clientShowName),
                    'paramCode': new FormControl(item.paramCode),
                    'paramType': new FormControl(item.paramType),
                });
(<FormArray>(this.detailForm.controls["paramsList"])).push(formGroup);               this.detailForm.controls['paramsList'].setValue(this.model.paramList);   
```

10. 編輯狀態將資料載入新增表單
# Question:
1. 該如何在html樣版上設定selected
2. 衍生上述情境另個頁面ts按照相同model但確無法綁定
3. 新增狀態下用手動輸入將必填元件資料給登錄後就正常，但編輯狀態下程式載入資料發現**儲存鈕**並無法調用?
4. 訊息:component.ts:232 ERROR Error: NG01002: Must supply a value for form control with name: 'paramType'，類似[[js語法]]特性後面指令無法正確執行
5. 已經排除上述訊息，但在載入時發現combobox並未填值
6. 檢查html中formControlName 、ts中FormGroup 都有名稱對應，Debug console也無錯誤訊息，但是表單無法將值給綁定
7. 為何編輯在完重新載入時發現原本列表疊加上去，ex:本來是表格4列，存檔後變成8列

10. Cannot read properties of undefined (reading 'invalid')
# Answer:
1. 只需value設定null即可，其預設ORDER BY最前面
```
SelectItemModel = {value:null,text:'請選擇',title:''}
```
2. 
- 檢查ts內是否有在**FormGroup**註冊
- 檢查html內是否在**formControlName**註冊，才能將FormGroup綁起來
ts:
```
this.detailForm = new FormGroup({
	'paramType1': new FormControl(this.detailData.paramType, [Validators.required]),
});
```
html:
```
select class="form-control" formControlName="paramType1">
	<option *ngFor="let opt of paramType1s"
		[ngValue]="opt.value">
		{{opt.text}}
	</option>
</select>
```
3. 直覺理解誤區以為只防呆空白，遺漏還有檢查格式，元件綁定日期格式如下
```
CustomValidators.date
yyyy-MM-dd error
yyyy/MM/dd
```
4. 若已經有用FormGroup後，所有key-value都要設定，其才會識別為相同型別
```
this.detailForm.setValue({
  'prodPolicyClauseId': this.detailData.prodPolicyClauseId || 0,
  });
```
5. 發現有的combobox內顯值為數字，但要綁定呈現時需轉成string
6. 檢查html中form標籤是否有設定
```
        <form class="form-horizontal" [formGroup]="form">
            form: FormGroup;
```
7. 真正原因為component內FormArray並無清空所導致，類似**參考**型別概念要清除源頭
```
this.model.paramList.length = 0; //ok
(<FormArray>(this.detailForm.controls["paramsList"])).clear(); //error
```

10. 載入到表單資料格式不符