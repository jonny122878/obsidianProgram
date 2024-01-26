---
date
aliases
---
# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
#資訊 #核心 
# Unify



#restructure

# 抽象結構
- 每個結構按照特性分為元素和集合，若是集合則帶有集合內**元素間分佈度量**
- 存取尺度:
  - 順序
  - 名目[[SQL string exception]]    
  - 間距[[SQL number exception]]
  - 倍率
  - 類別
- [[SQL NULL exception]]
# PK組成
- Portfolio Product ProductID ProductGroup
- Product ProductID ProductGroup
- 這是不同的東西只是組合商品為了產生**最小單位識別**單一項
# 單位組成
- 時間顆粒度
- PK識別此筆資料唯一
- FK外部集合連結到此的欄位
- 分類(可用來Where或Group)
- 細節紀錄(可用來Where或數值運算)

# C衍生結構
- 帶有key字典，延伸ILookup(可以有重複概念)
 - 每個元素一樣List，延伸Array(實值型別)
# 系統設計
- NULL情境適用combobox default都未選擇情況
