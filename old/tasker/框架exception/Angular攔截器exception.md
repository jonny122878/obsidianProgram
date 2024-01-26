# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::2
Review::

#知識    #work 
# Unify
- 檢核數字大小是有考慮到小數位
- 日期格式通常都有內建攔截器






1. #flashcards 
- Highlight:有一表單需要做百分比填寫，防呆如下
```
'appFeeRate' : new FormControl(item.appFeeRate, [Validators.min(0),Validators.max(100)]),
```
- Question:是否包含小數防呆?
?
- Answer:從Angular**只有number型別**直覺推論並無區分整數、小數，可直接防呆小數

2. #flashcards 
- Highlight:Angular本身可以設定**AOP屬性**來達到表單防呆效果，ex:C# Model設定
html:
```
<button type="button" class="btn btn-primary" (click)="save()" [disabled]="detailForm.invalid"></button>

```
component.ts:
```
ngOnInit(): void {
	this.detailData = <ProdClauseDetailFormModel>{};
	this.detailForm = new FormGroup({
	'version': new FormControl(this.detailData.version, [Validators.required]),
});
```
- Question:新增狀態下用手動輸入將必填元件資料給登錄後就正常，但編輯狀態下程式載入資料發現**儲存鈕**並無法調用?並丟出Cannot read properties of undefined (reading 'invalid')
?
- Answer:載入資料是否符合驗證，元件綁定日期格式如下
```
CustomValidators.date
yyyy-MM-dd error
yyyy/MM/dd
```


3. #flashcards 
- Highlight:
- Question:
?
- Answer: