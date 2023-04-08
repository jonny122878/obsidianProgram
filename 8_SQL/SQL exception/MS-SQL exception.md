
[[exception 規範]]

## 結構上
- insert若是流水欄位要移除

 




## 關聯式
- 錯誤訊息:轉換出來筆數不一致
- 情境:預存程序將原本資料計算轉換成產出結果表,INSERT INTO SELECT 語句
- 判別:
   - 發現以下特性:
   - 因為主表為使用者建檔,有key空白,導致 INNER JOIN 要撈取資訊配對不到
   - 直覺將主表改成LEFT JOIN,但是衍生出新的問題,因為所要撈取副表key-value為1-M關係
   - 衍生出數量變成乘積狀態
   - 解決方式:先將副表內key-value 弄成 1-1關係.在透過LEFT JOIN方式也可避免掉數量可能為少情況
   - **INNER JOIN**也是有可能會造成數量乘積特性,若右側數量與左側key配對不是1-1關係情況
   - 語句若是用來更新資料,那就要確保主表JOIN不管幾張副表從頭到尾都必需數量一致

- 錯誤訊息:轉換出來資料會有覆蓋情況
- 情境:預存程序UPDATE JOIN 所要更新資料
- 判別:JOIN第一張副表為1-1,第二張為1-M
- 但是我要取得第二張副表來進行更新,第一張表只是中介key表格
- 可用子查詢第一與二給處理過後在JOIN主表
- 最後要確認JOIN每個副表都是要1-1情況


## 語法錯誤

- 錯誤訊息:在有預期條件內容指定非布林運算式,接近BEGIN
- 判別:IF條件式沒寫好


- 錯誤訊息:除非同時指定了TOP、OFFSET或FOR XML，否則ORDER BY在檢視表、內建函式、衍生資料表、子查詢及通用資料表運算式中均為無效
- 情境:撈取表格指定到MS-SQL變數內
- 判別:

- 錯誤訊息:找不到預存程序 SP_EXCUTESQL
- 情境:
- 判別:只能在預存程序語法上執行

- 錯誤訊息:在函式中使用副作用運算子,'INSERT EXEC' 無效
- 情境:
- 判別:函式本身只能是純函式,不能帶有更改其它表功能


- 錯誤訊息:當SQL要改成用string取組合時,單引號exception
- 情境:
- 判別:'''' + 'string' + '''' ,等於一個單引號特殊符號區別''''

- 錯誤訊息:資料類型ntext不可用UNION、INTERSECT 或EXCEPT運算子的運算元，因為不相容
- 情境:
- 判別:'型別規範問題,用nvarcahar(max)可解決

## 臨界自動判別

- 情境:當欄位為空字元調用SUBSTRING
- 判別:'類似型別特性不會exception,return 空字元

- 情境:aggrgate function ex:MAX、MIN，若此集合為空則return?
  - NULL

- 情境:Where條件式整數與小數做比較return?
  - 小數位需指定到確切位數，否則不成立
  - ex 65.42 < 65 exception
  - 65.42 < 65.00

- 情境:AVG在不同數字型態return?
  - 其小數點會依據型態做進位
  - ex:int計算出來值就不可能有小數位數值 

###### MAX_NULL_example
```
SELECT MAX(Time)
FROM [TestNote].[dbo].[TestDate]
WHERE Time < '20210306'
```

- 情境:UPDATE INNER JOIN 副表與主表為1-M關係,其會如何替換?
- 判別:只替換M數量表格第一筆

- 情境:UPDATE INNER JOIN 副表A 100 副表B 105 主表其會如何替換?
- 判別:最後表B為數量基準

- 情境:Select中WHERE陳述式放在子查詢,與放在JOIN外層差異?
- 判別:放在外層是已經產生JOIN結果在WHERE過濾,二者看起來相同,但實際執行會有數量不同情況

- 情境:UNION產出資料不如預期?
  - 檢查再做接合時SELECT FROM後面不要有其他關鍵字
  - 檢查接合表格是否有重複資料



## Group
- 若要分組有依據日期年度但欄位為日期型態有辦法放在Group陳述內?
  - 因日期函數return為單一值因此放此處不影響
- 資料行 '...' 在選取清單中無效，因為它並未包含在彙總函式或 GROUP BY 子句中?
  - 因SQL Group無帶有投射性質，需注意Select與Group陳述式欄位數量一致 
## Order
- Order陳述式內是否可放置函數?
  - 可 

