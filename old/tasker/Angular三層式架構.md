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
#資訊 #work 
# Unify


# 第二層分類商業邏輯層
- module.ts 接收後端相關資訊
- service.ts 打通和**後端API**通訊，Injectable裝飾器區別功能
- module.ts 提供註冊點給單一頁面註冊，NgModule提供註冊點
- template.html 提供頁面點給單一頁面覆寫
- component.ts 主頁面跟使用者互動共用模式，ex:唯讀、新增.....
# 第三層單一頁面邏輯
- template.html:單一頁面獨特畫面
- module.ts:註冊key註冊到第二層用，NgModule提供此零件所含模塊
- component.ts:負責單一頁面使用者互動，商業邏輯相關都調用第二層service.ts，Component裝飾器提供html key，讓第二層html調用

# 頁籤式元件
- ngOnInit:載入一次性，ex:service combobox來源、資料庫內動態元件
- ngOnChange:初始化form元件、裝飾器填值、是否可編輯狀態判別