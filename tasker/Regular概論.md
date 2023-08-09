---
data
aliases
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:
Author:
Note Type:
Topics:
#work 
# Evergreen Note
Highlight:
Question:
Answer:
# Summary
- 符號是**類別尺度多個字元**都符合此條件,但它還是**單一字元**為單位
- pattern用**字元**為單位從左往右遍歷,到符合**單一字元**後打住
  - 若pattern超過一個字元則打破此規則
  - 限定符亦是打破此規則,變成終點邏輯自訂要貪心、非貪心
- 用Reg寫防呆時特別考量[[不好判別exception]]
- [[Reg C語言]]實現Regular 特性
- [[RegExp javascript語言]]實現Regular 特性
# Note
## 情境
- query commit點
- OS系統下檔案重新命名
- 抓取文章單字:\b.\b
## limit
|符號|功能|備註|
|:---|:---|:---|
|+|貪心|從符合字元開始找到不符合字元才停下|
|?|非貪|找到符合字元停下|
|* |可有可無|0-N次|
|\w|英文大小寫數字+符號_|核心設計符號不匹配|
|\b|字元||
|{m}|最少次數||
|{m,n}|限定範圍||
|[\u4e00-\u9fa5]|中字類別尺度||
|\s|任意空白字元|含tab、space...|
|[]|此字元為框內的字元就算相符|or邏輯效果|
|^|開頭|原本目標+匹配模式，再多加的限定符|
|$|結尾|原本目標+匹配模式，再多加的限定符|
