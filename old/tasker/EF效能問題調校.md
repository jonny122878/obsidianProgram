# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::
Review::

#資訊 #work 
# Unify


### 使用操作
- 實體化展開時機為最後呈現ex:View和File，延伸可透過Repo封裝
- 當讀取資料不做任何異動時,可用AsNoTracking
- EF SaveChange 本身是帶有Tran
### 系統設計面向
- 讀寫資料庫分離,在透過MS-SQL內建方式同步
- 讀寫分離設計讀取DB結構可以弄成非正規化減低JOIN，或是用View檢視表
- 針對user對特定資料讀多寫少狀況弄成cache,將讀多資料特別撈出來到List上,跟著Request消失,或是Thread定期更新