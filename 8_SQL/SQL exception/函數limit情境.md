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

#
SQL **function**本身不丟exception,可以想像成是弱型別,是透過丟出結果判別錯誤


# Highlight:

# Question:
1.1 SUBSTRING('test',0,1) 
1.2 當欄位為空字元調用SUBSTRING
2.aggrgate function ex:MAX、MIN，若此集合為空則return?
  - NULL

# Answer:
1.其都為字串,因此return **空字元**
2.因其aggreagte input型態會有多種,因此用萬用型態**NULL**表達
