---
date
aliases
---
# Metadata
Status:發芽
Source Type:金財通
Source URL:
Project:
Author:
Note Type:
Topics::前端、框架、前端框架、review
#資訊 #work 


- 將檔案綁和SRP裝飾器應用結合，並且如何injection寫入
- NgModule 補齊


# Unify
- 開始環境配置[[Angular環境設定exception]]
- 用[[TypeScript語法]]去撰寫
- 綁定為各單位之間溝通很重要概念，無論單位為模塊、父子、層次...都是透過分割成單位後綁定將其溝通串起來
- 增加業務邏輯層可優化[[Angular三層式架構]]

# 模塊間綁定方式溝通
## 檔案綁定
- [[Angular元件綁定exception]]
- [[Angular不丟exception]]
- [[Angular變數生命週期exception]]
- [[Angular攔截器exception]]
- View => html、css
- ViewModel => component.ts
- Register component => module.ts
- API => service.ts
- Model => module.ts
## 模塊綁定
- 插值綁定(component => html): ex:table呈現 
- 屬性綁定: ex:編輯狀態表單填值 
- 事件綁定(html => component): ex:提交表單
- 雙向??

```
{{value}}
[value]="name"
(click)="save()"
```
## 階層綁定
- [[Angular裝飾器exception]]
- Output 子 =>父。ex:首頁上方查詢表單按鈕事件
- Input 父 => 子。ex:下拉選單來源散落在多個新增頁籤頁面
## 階層綁定範例情境解說
首頁表格中表格列有編輯鈕，click後進行將此列資料跳轉到編輯頁面
- 表格列檔案如下:先找出Output中裝飾器名稱當key去主html搜尋
```
prod-clause-query-list:
html:
ts:
@Output() editClick = new EventEmitter<CommonQueryModel>();
edit(data: DmCommonPolicyClauseInfoModel): void {  this.editClick.emit(this.commonQueryKey);
}
```
- 主html如下:
- 用Output key去找到指定方法，並且用方法當key
- 用方法key再找對應html區塊別名
- 區塊之間放入ID做識別
- 透過html區塊method取找出對應區塊ID
```
<prod-clause-query-list #clauseList
(editClick)="clauseDetail.edit($event);
<prod-clause-detail-form #clauseDetail
```
- 編輯頁面結構如下:再用剛剛方法key去找對應component方法
```
prod-clause-detail-form
ts:
add(): void {
```

# 底層實作精神
## SRP精神透過裝飾器將其按照職責區分
- 基礎Component:負責此頁面顯示功能
- Injectable :負責後端HTTP溝通、特殊業務邏輯ex:Prase Json
- pipe:將其想成extension method
```
{{ ctrl.value | currency  : '' : '' : "0.0" }}
```

- Directive:類似ASP.NET 將其翻譯成DOM
  - 結構型:ngFor、ngIf對DOM 新、刪
  - 屬性型:ngModel DOM樣式修改
  - 調用方式先在module註冊後，html屬性加入selector
```
@Directive({
    selector: '[amountFocusoutFormat]'
})
```

## SPA精神
- 物理上只有一個頁面，就是app.component.html
- 達到多頁面效果
  - 透過app-route.model.ts (模擬不同網址單一頁面生成不同元件)
  - app.component.html中router-outlet標籤 (模擬不同網址單一頁面生成不同元件)
  - app.module.ts (元件註冊)

- 實作概念[[前端語言框架發展史]]


## 模塊間綁定(目前暫且看不懂) ??
- module.ts register component.html 和MVC中Controller與View**倒置**，此職責用來app能識別
- component register model、service
