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
1.用多個DataTable存檔時跳出不存在資料表
2.集合已修改,列舉作業可能尚未執行
3.SESSION的DataTable要匯出檔案，但其匯出時因匯出欄位不需要將其給移除
5.使用者希望數字呈現為千分位
6.調用考量可維護性[[DataTable移轉資料順序與名目尺度選擇]]
# Question:
1.調用DataSet.Tables.Add(dt);時跳出標題訊息
2.展開要修改DataTable foreach Remove DataTable Column
3.在Page_Load丟出無此資料行，但明明SESSION中DataColumn並無做移除4.array進行運算時為不固定能否透過string[] = new string[]{} 
5.是否能在DataColumn內直接將型態改成string，在將其改成千分位文字格式
# Answer:
1.物件**初始化異常**通常不excption而填入預設值
DataTable不管是其預設TableName都是為 Table1
因此若無規範加入到DataSet就會有二個相同TableName
2.做迭代器之類操作是不能直接修改展開集合來源
3.指派匯出時DataTable資料來源修改透過 = 方式無作用
，因其為**參考型別**上述方法為淺複製，可透過Row.Add、.NewRow 還需要Rows.Add
4.不能，因其為**實值**型別，在造訪效能上比List更快
5.DataColumn**綁定DataTable後**就不能在修改型態，會丟出資料行擁有資料後就無法在變更DataType