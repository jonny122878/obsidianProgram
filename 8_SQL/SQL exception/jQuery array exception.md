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
1.將選取器丟入$.each來源進行展開
# Question:
1.進行元素選取器方法無法做操作
# Answer:
1.選取器可將其想成是一個**集合**，展開後元素型態會是**HtmlElement**

- 疑惑點:因其弱型別特性,假如selector集合做filter後return string
- 情境:
- 判別:其還是會遵守filter特性,只做**數量過濾**動作,自動將return value轉成原本型別

