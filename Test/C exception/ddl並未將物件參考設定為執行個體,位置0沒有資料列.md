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
為何選取ddl會出現如下:
  - ddl.SelectItem.Text=''，並未將物件參考設定為執行個體
  - ddl.SelectedIndexChanged，位置0沒有資料列
# Answer:
  - 所點擊ddl帶有**階層特性**，子來源下拉來自父下拉，但是為PostBack觸發子下拉來源尚未載入
  - 使用者尚未選取任何項目，程式**其他邏輯**判別用此來做清空
  - 副程式調用UI狀態時，為了避免切換狀態後又重新切換回來，因此調用時一開始都先再用一次預設狀態
