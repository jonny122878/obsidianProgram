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
#知識 

# Unify
- javascript特性若**語法錯誤**Console看不出來，繼續跑
- html模塊若**通信key名稱**不同不丟任何錯誤，依循SRP準則

# Highlight:
1. 子html列表顯示條件為其他子html內combobox值決定
2. combobox select value為數字
# Question:
1. 並沒有按照條件做顯示與否
2. 為何防呆條件無法成立
# Answer:
1. FormGroup名稱無對應
```
//子html
<normal-commission-list #normalcomiList 
[ngClass]="{'hidden': comiRateSettingDetail.detailForm.value.commissionType != 1 }">
//子component
'contextType': new FormControl(this.detailData.contextType, [Validators.required]),
```
2. 語法錯誤，javascript特性無丟exception
```
(result.clauseType == 2) ? false:true; //ok
(result.clauseType = 2) ? false:true;  //error
```