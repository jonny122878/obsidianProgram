[[exception 規範]]

- 疑惑點:當我再產出DataTable之後DataRow(0)並沒有按照條件式指定第一筆邏輯計算結果
- 情境:用foreach搭配i++(順序計數)將DataTable展開內部為DataRow按照邏輯計算規則產出另個DataTable
- 判別:
- 計數擺放順序問題，若計數為了填入欄位次序放在前面，那後續欄位條件式又根據此計數判別則會條件式約束到下一筆


- 錯誤訊息:無效的引數
- 情境:函數為物件或集合(參考型別)
- 判別 :檢查再調用函數注入參數時,可能因特定情境導致參數無實體化

- 錯誤訊息:每個DataTable最後一筆都進行特定計算
- 情境:針對資料庫特定欄位時,會針對DataTable最後一筆進行特定計算
- 判別 :
  - 再用條件式約定特別情境判別時,需要考慮最原始需求進行條件傳接,ex:特定情境+最後一筆
  - 僅量用最原生做條件,最原生為資料庫特定欄位就不要用按照資料庫特定欄位規則所產生不同樣式UI元件

- 錯誤訊息:其為命名空間但被當作變數使用
- 情境:程式調用UserControl,但我的工具命名空間有NetAP.UserControl
- 判別 :
  - using SinoPac = NetAP.UserControl;此方法無效
  - 命名空間與類別**同名**時,只能在類別前面用命名空間做區別


- 錯誤訊息:再調用Regular Match Group時,將其轉成List型別,但不能使用Group["name"]語法
- 情境:
- 判別 :只能為Collection結構才有Name這樣名目尺度指定



- 疑惑點:function override時return參數名稱相同,但回傳值結構不同
- 情境:
- 判別:無法用return當override,因為在調用function可以不用return

- 疑惑點:宣告新namespace時無法做引入,IDE找不到
- 情境:
- 判別:可能資料夾並沒有引入到sln內,簡易方法直接delete後重新建資料夾

