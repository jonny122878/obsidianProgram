---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:
1. 有一表單需要做百分比填寫，防呆如下
```
'appFeeRate' : new FormControl(item.appFeeRate, [Validators.min(0),Validators.max(100)]),
```
# Question:
1. 是否包含小數防呆?
# Answer:
1. 從Angular只有number型別直覺推論並無區分整數、小數，可直接防呆小數