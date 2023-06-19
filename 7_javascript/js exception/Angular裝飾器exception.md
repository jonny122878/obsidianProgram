---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:
1. 想要在父module.ts做一個下拉選單全部來源，後續在透過注入到子module.ts
```
@Input() dropdownInitData: InitDropdownData;
```
2. 下拉選單共用子元件引入
3. 問卷資料父component透過Input載入
# Question:
1. 為何明明後端API是有資料的，將方法搬子module.ts呼叫service也是有值，但透過父module.ts呼叫service無值
2. Can't bind to 'action' since it isn't a known property of 'comirate-setting-query-form'.?
3. If 'quote-question-form' is an Angular component and it has 'questionData' input, then verify that it is part of this module.
# Answer:
1. **異步**觀念，每個component呼叫時間不盡相同，可透過setTimeout處理
2. 子表單無declare component
3. 主html有用Input屬性綁定，但子component成員內Input屬性名稱無對應到