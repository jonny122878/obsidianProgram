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
附件檔案要搬移，需要針對單號欄位編碼移動位置判別，但有的單號為空白

# Question:
解法方式想要寫法精簡，透過短路式先行判別長度後後在截斷字串
```
len > ... substring ...  //或是
WHERE IS NOT NULL <> ''
```
# Answer:
MS-SQL計算原理為先計算一層後，在透過此層在前推一層，而不是二個條件推一層
ex:
100 => LEN() >  => 10 => substring => 5
按照如上原理，因無過濾因此還是丟exception
衍

