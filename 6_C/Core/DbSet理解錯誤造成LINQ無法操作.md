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
1.具有陳述式主體Lambda運算式，不可轉換成運算式樹狀結構 IQueryable
# Answer:
12.DbSet inherit IQueryable 延遲查詢調用，因此若要用LINQ要先AsEnumerable，而不是透過用本來資料表去弄
