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
## 抽象結構
- 每個結構按照特性分為元素和集合，若是集合則帶有集合內**元素間分佈度量**
- 存取尺度:
  - 順序
  - 名目:
    - [[字串或二進位會被截斷]]
    - [[不允許資料類型varchar隱含轉到varbinary(max),請使用CONVET function]]
  - 間距
    - [[轉換numeric、int到資料類型numeric時發生算數溢位錯誤]]
    - [[位於資料表 'TableName' 的識別欄位其外顯值只有當使用了資料行清單且 IDENTITY_INSERT 為 ON 時才能指定。]]
  - 倍率
  - 類別
### PK組成
- Portfolio Product ProductID ProductGroup
- Product ProductID ProductGroup
- 這是不同的東西只是組合商品為了產生**最小單位識別**單一項
### 單位組成
- 時間顆粒度
- PK識別此筆資料唯一
- FK外部集合連結到此的欄位
- 分類(可用來Where或Group)
- 細節紀錄(可用來Where或數值運算)

### C衍生結構
- 帶有key字典，延伸ILookup(可以有重複概念)
 - 每個元素一樣List，延伸Array(實值型別)
# Note


