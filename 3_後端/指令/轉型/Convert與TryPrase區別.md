
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
如標題
# Question:
# Answer:
應盡量用TryPrase
```
decimal d=0;
decimal.TryPrase("str",out d);
```

好處在於不會丟**exception**,並且會能吃其他類型數字格式文字,ex:1,000,000
int.TryPrase也有類似效果




