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


MS-SQL **function**本身不丟exception,可以想像成是弱型別,是透過丟出結果判別錯誤


# Highlight:
4. 新增資料進行防呆時要檢查目前此筆資料為第幾版號
# Question:
1. SUBSTRING('test',0,1) 
2.  當欄位為空字元調用SUBSTRING
3. aggrgate function ex:MAX、MIN，若此集合為空則return?
  - NULL
4. 在LINQ中使用WHERE後MAX丟出exception
# Answer:
1. 其都為字串,因此return **空字元**
2. 同上
3. 因其aggreagte input型態會有多種,因此用萬用型態**NULL**表達
4. MAX本身並無防呆NULL情境，從名稱直覺並無FirstOrDefault
5