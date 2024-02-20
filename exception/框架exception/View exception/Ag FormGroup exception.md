# Metadata
Qty::4
Review::
Restructure::3 relation

### Think

# Exception


1. #flashcards 
- Highlight:編輯狀態表單頁面載入
- Question:表單都為唯讀狀態
?
- Answer:載入畫面因此表單無值所有用if擋掉填值表單，但其預設若無setValue 表示無初始化會disabled()

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
- Highlight:
- Question:
?
- Answer: