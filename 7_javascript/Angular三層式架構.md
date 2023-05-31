---
data
aliases
---
# Metadata
Status:發芽
Source Type:金財通
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
#### Register
其原理為app原始層定義出html => 
第二層商業邏輯層主html頁面 override app=> 
第三層在由單一頁面 override 

##### 第二層分類商業邏輯層
- module.ts 接收後端相關資訊
- service.ts 打通和**後端API**通訊
- module.ts 提供註冊點給單一頁面註冊
- template.html 提供頁面點給單一頁面覆寫
- component.ts 主頁面跟使用者互動共用模式，ex:唯讀、新增.....
#### 第三層單一頁面邏輯
- template.html:單一頁面獨特畫面
- module.ts:註冊key註冊到第二層用
- component.ts:負責單一頁面使用者互動，商業邏輯相關都調用第二層service.ts


# Note
