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

# Question:

# Answer:
TRANSCATION本身也有**區塊修飾子**特性，因此無須特別在用BEGIN END區塊，且用COMMIT、ROLLBACK此種也有**區塊修飾子**特性結尾
false
```
BEGIN TRANSCATION
END
```
true
```
BEGIN TRANSCATION

IF @@ERROR = 0
BEGIN
	COMMIT;
END
ELSE
	ROLLBACK;
END

```
