---
data
aliases
---
# Metadata
Status:發芽
Source Type:工作
Source URL:
Project:
Author:
Note Type:
Topics:

# Evergreen Note
Highlight:
Question:
Answer:
# Summary
[[excel匯入失敗，出現insert很多欄位空白訊息]]
# Note


- except
- 是否資料正確移轉
- 確實發信
- 後面有調用此表計算是否正常
## 計算
- 數量不一致
    - 原始來源不同
    - 來源更新
    - 驗證來源不同ex:二者更新間不一致
    - 轉檔異常
    - Join過濾掉
- 期望值有值但不一致
    - 類別尺度轉換limit ex 小數點認定
    - 特殊值認定 ex Null補0

- 轉型
  - 字串做截斷長度不足
  - 字串分割成陣列要處理超出索引值
  - 無確定字串變數是否為NULL
- 檔案讀寫
  - excel是否有user正在用
  - excel cells格式
  - excel sheet名稱或次序
  - excel是否存在
  - excel用LINQ套件載入空白cells為null
  - txt是否存在
  - db連線
  - db連線字串和regedit吻合
  - 有的OS copy 原本存在file會蓋過其create time