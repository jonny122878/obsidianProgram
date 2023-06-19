---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸、金財通
Author:
Note Type:
Topics:

# Unify


# Highlight:
1. 在Angular中迴圈滾出來radioButton過於接近，無任何間距
2. 容器調整
3. user點擊送出鈕後要將按鈕區塊給hidden避免重複發送
4. 實作表格
5. 衍生上述因為td位置有大有小,而去設定width絕對尺度
6. 同上
7. 表單為編輯狀態
# Question:
1. 為何在中間插入空白符無效情況
2. 在調整容器過程中，該如何視覺上準確知道目前容器浮貼程度
3. 後端直覺Visible，但似乎不是所有標籤都有此屬性
4. table切版在呈現時希望有的儲存格做合併情況
5. tr本身是按照內部有幾個td去平均分佈所佔位置，但若用width**絕對**尺度,每個td加總tr不盡相同，**常理推論**不可能一個tr2000,一個1000,變成表格不在是方形情況
6. 用width**絕對**尺度內部td給調寬但是沒有如預期將其撐開
7. 屬性readonly、disabled該如何選擇?
# Answer:
1. 在html中空白符為特殊符號
```
&nbsp;
```
2. 用border讓其畫線即可
3. 透過css中display=none
4. 在td屬性加入指令如下

|css|效果|
|:---:|:---:|
|rowspan|往上下合併|
|colspan|往左右合併|
5. 當表格列有衝突時會用tr最大值為基準
6. 使用width絕對屬性,其邏輯上不可能會超出所在**容器寬度**情況
7. readonly不能有keyborad event,但是可以**focus與copy**
