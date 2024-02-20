---
data
aliases
---
# Metadata
Status:發芽
Source Type:心得
Source URL:
Project:
Author:
Note Type:
Topics:

# Evergreen Note
## Highlight:
1.撰寫一個全新的SQL
2.已經有寫好SQL要做擴充或Debug
## Question:
是否有一定的評估準則?二者先後步驟是否相同?
## Answer:
###### 了解未知SQL時
- Debug時可先預覽[[SQL抽象結構]]與[[SQL抽象查詢]]快速掌握違反規範limit點
- Debug順序時INNER為主，其為必要值或是帶有**過濾**動作
- LEFT則是補足資訊，應可之後在了解
###### 集合產出整個workflow類似樹狀概念,不斷往下遞迴,每個階層都是做下述4個步驟
  - 是否產生新集合
  - 集合之間結合方式
  - 每個集合單位換算
  - 每個集合整平資訊
- 最後將整個集合排序
若要SQL撈取結果寫成PROCEDURE參考[[MS-SQL語法]]


# Summary
## 是否產生新集合
- 過濾條件是否需要**Group** 產生新集合 (待整理,排程掛計算)
  - 則先將集合分離成原本資訊集合、過濾條件集合
  - 過濾條件集合再看有幾個Group去巢狀得到結果
- 若過濾有用到相對形容詞,ex:前幾月,就需透過ROW_NUMBER生成相對應過濾欄位
[[SQL Group述句exception]]
## 集合之間結合方式
- 交集之前考慮點
  - 欄:資訊的不足再擴充:要將NULL值給填補利用LEFT JOIN
    - 確保key之間關係條件數量為M-1
    - 通常情況為記錄檔取得基本檔資訊
  - 列:原本資料量再增加:UNION
  - 是否進行過濾目的 :剔除不需要的資料INNER JOIN
    - 過濾時確保數量為1-1,否則會產生乘積
    - 若數量為1-M除非為表頭配對表身,此種才不會exception
  - 差異比較EXCEPT
    - 基準放主表
    - 驗證放副表
    - 注意數量邏輯誤區 
  - 確認是否除法情境:二個集合中其中一個集合元素和另個集合內所有元素都有關係
  - 主表數量有遺漏狀況:利用CROSS JOIN補足成主檔
  - 確認交集之前表的顆粒度單位整合同單位
[[SQL概念 JOIN述句邏輯exception]]
[[Zip應用]]
- ex:主表決定
  - 做交易檔撈取時，觀察損益檔是否帶有庫存
  - 若帶有庫存則應以此為主表，無庫存表示當日無持有部位

## 每個集合單位換算
- where時間切片：ex:每日、或是訂單
  - LINQ[[SQL Where exception]]
- where環境顆粒度：ex:大數據維度部門、交易員
- sum+group:ex:時間顆粒度提升日到月
- avg+between
- order+max,min:集合測度
- where冗餘資料
- 過濾條件帶有相對性形容詞
  - 日期函數:GETDATE、DATEADD、DATEDIFF
  - 子查詢 
  - [相對形容詞](######相對形容詞_ex)
###### 相對形容詞_ex
- ex:抓取**前一日**信評
- ANS:帶有**相對形容詞**MAX搭配子查詢表格
- ex:過濾掉某個基本的一些資料
- ANS:過濾帶有**相對資料性**可用WHERE搭配子查詢
## 每個集合整平資訊
- 編碼:collate Chinese_Taiwan_Stroke_CI_AS 編碼大小寫不符、字型...
- CASE WHEN:類別尺度移轉
- CONVERT:不同型態轉型並且資料格式處理
- As:從這表格來源
- IsNull
- 需要order scale,ROW_NUMBER
- [[邏輯盲點]]
[[SQL GUID apply]]

## 將產出結果給排序
小心不符合預期值ORDER[[combobox來源ORDER BY default疑問]]
編碼誤區[[SQL Order exception]]
LINQ理解bool誤區[[LINQ檔案散落各處路徑ORDER是否存在]]

若為排序規則為一個以上欄位,可透過如下語法,達到LINQ ThenBy效果
```
ORDER BY [updatedate] DESC ,[updatetime] DESC
```

# Note


