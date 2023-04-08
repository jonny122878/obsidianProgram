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
INSERT SQL用 'result' 寫到varbinary(max)丟出標題上訊息
# Question:
應都是string型態,為何丟出如上訊息
# Answer:
varbinary本質已經**跳脫** char、nchar、varchar、nvarchar這些規則,可以想成是另種類似string型態了