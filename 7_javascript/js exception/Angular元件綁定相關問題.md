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
# Question:
1. 該如何在html樣版上設定selected
2. 衍生上述情境另個頁面ts按照相同model但確無法綁定
3. 新增狀態下用手動輸入將必填元件資料給登錄後就正常，但編輯狀態下程式載入資料發現**儲存鈕**並無法調用?
4. 訊息:component.ts:232 ERROR Error: NG01002: Must supply a value for form control with name: 'paramType'，類似[[js語法]]特性後面指令無法正確執行
5. 已經排除上述訊息，但在載入時發現combobox並未填值
6. 檢查html中formControlName 、ts中FormGroup 都有名稱對應，Debug console也無錯誤訊息，但是表單無法將值給綁定
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