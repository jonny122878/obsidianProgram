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
## Startup:
- [[模塊相依性與遺漏設定造成錯誤]]

## Model:
### 表格操作設定
- 綁定方式是透過屬性名**必須等於**欄位名,類別名**必須等於**表格名
- 設定欄位在AP上呈現名稱、防呆規則。
- [[結構綁定因遺漏設定造成異常]]

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
- [[DbSet理解錯誤造成LINQ無法操作]]

## Controller[[
Core Controller特性]]:
#### Web
- 考慮驗證相關錯誤或成功訊息用ViewBag呈現
- 初次造訪 return View
- 驗證錯誤 return View，並填入ViewBag好知道錯誤
- 驗證成功 return Redirect，導向
#### API
- 若為API無須考慮View相關錯誤訊息ViewBag...
- 初次造訪 return JsonResult
  - [[Prase API JSON發現都沒資料]]
- 驗證錯誤(因沒有畫面用httpCode替代) ?
- 驗證成功(因沒有畫面用httpCode替代) ?
## View:
- 將object model轉成Controller所注入強型別
- 綁定時[[View丟出Object reference not set to an instance of an object]]
- 集合與元素衝突[[IEumerable轉Table該如何綁定欄位名與值]]
- [[Model型態綁定到View相關錯誤設定]]
# Note
