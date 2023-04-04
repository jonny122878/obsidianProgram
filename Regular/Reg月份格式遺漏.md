---
data:2023-02-24
aliases
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project:租貸
Author:
Note Type:
Topics:Regular Expression

# Highlight:
AP檢驗月份日期是否正確,直覺反應用二個數字規則約束,但月份一月到九月**前面數字**都要是0,十月到十二月**開頭都是1**,尾數只能0~2
# Question:
按照規則分析,是有二種條件,是否需要用二個re去檢驗
ex:
```
bool isOne = ....
bool isTen = .....
if(isOne || isTen)
```
# Answer:
條件用()去包覆,之後在透過[]符號類似SQL WHERE IN ()
[(0?\d)|(1?[0-2])]
實作語言[[Reg C語言]]
