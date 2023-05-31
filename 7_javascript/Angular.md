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
- 實作概念[[前端語言框架發展史]]
- 環境配置[[Angular環境設定相關議題]]
- [[TypeScript]]
- [[Angular三層式架構]]
## 構造
綁定為各單位之間溝通很重要概念，無論單位為模塊、父子、層次...都是透過分割成單位後綁定將其溝通串起來
#### 本身模塊與模塊之間溝通是透過綁定方式去呈現
###### 模塊之間綁定
- [[Angular綁定轉型相關議題]]
- [[Angular元件綁定相關問題]]
- View => html、css
- ViewModel => ts
- Model => 後端來源
###### 父子層之間綁定
- Output 子 =>父。ex:首頁上方查詢表單按鈕事件
- Input 父 => 子。ex:下拉選單來源散落在多個新增頁籤頁面
###### html父層區塊之間綁定
- 區塊之間放入ID做識別
- 透過html區塊method取找出對應區塊ID
- 找到區塊ID再找出對應資料夾
- 資料夾內子html對應component
```
<prod-clause-query-form (queryClick)="clauseList.query($event)">
<prod-clause-query-list #clauseList>
```

綁定方式分為單向View、ViewModel、雙向
#### 再透過發揮SRP精神透過裝飾器將其按照職責區分
- 基礎component => 負責此頁面顯示功能
- service => 負責此頁面業務邏輯功能
- pipe => 將其想成extension method
#### 發揮SPA精神
- 物理上只有一個頁面，就是app.component.html
- 達到多頁面效果
  - 透過app-route.model.ts (模擬不同網址單一頁面生成不同元件)
  - app.component.html中router-outlet標籤 (模擬不同網址單一頁面生成不同元件)
  - app.module.ts (元件註冊)
#### 模塊間綁定
- module.ts register component.html 和MVC中Controller與View**倒置**，此職責用來app能識別
- component register model、service

# Note
