---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:江
Author:
Note Type:
Topics:


# Highlight:
# Question:
# Answer:
### 使用操作
- 實體化展開時機為最後呈現ex:View和File，延伸可透過Repo封裝
- 當讀取資料不做任何異動時,可用AsNoTracking
### 系統設計面向
- 讀寫資料庫分離,在透過MS-SQL內建方式同步
- 針對user對特定資料讀多寫少狀況弄成cache,將讀多資料特別撈出來到List上,跟著Request消失,或是Thread定期更新