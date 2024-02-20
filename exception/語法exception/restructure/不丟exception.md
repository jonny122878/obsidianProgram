


#資訊    #work 

# Unify


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







7. #flashcards 
- Highlight:
- Question:點擊新增按鈕明明formArray有增加，但html無效果
?
- Answer:發現tr標籤移除model，但html並無移除
```
*ngIf="item.value.isEdit"
```



10. #flashcards 
- Highlight:
- Question:
?
- Answer: