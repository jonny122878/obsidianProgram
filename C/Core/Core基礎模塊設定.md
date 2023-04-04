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
## Model:
### 表格操作設定
- 綁定方式是透過屬性名**必須等於**欄位名,類別名**必須等於**表格名
- 設定欄位在AP上呈現名稱、防呆規則。
- 設定用屬性在表格是否為PK,一定要設定否則[[the entity type requires a primary key to be defined]]

### DbContext(資料庫溝通)
  - inherit 
  - injection conn
    - 透過Service設定,需自行在override有建構子參數方法
      - appsetting.json設定連線字串
      - 注意keyword[[keyword not support datasource]]
    - 內建override OnConfiguring 
```
using System.ComponentModel;//default
@Html.DisplayName 
using System.ComponentModel.DataAnnotations;
using System.ComponentModel.DataAnnotations.Schema;
```
- [[EF效能問題調校]]
## View:
- 將object model轉成Controller所注入強型別
- 綁定時[[View丟出Object reference not set to an instance of an object]]
- 集合與元素衝突[[IEumerable轉Table該如何綁定欄位名與值]]

# Note
