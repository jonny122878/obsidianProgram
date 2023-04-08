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
原本附件檔案會分別存放在三個路徑中其中一個路徑，需求是要將目前所存放檔案給移轉到另個位置
# Question:
分析解法是透過LINQ GROUP BY以檔案為Key，路徑為Enumerable，透過此方式ORDER BY用檔案是否存在bool當條件，取最前面的
# Answer:
直覺true > false，但實際false > true