# Metadata
Qty::7
Review::
Restructure::

### Think

# Exception


1. #flashcards 
- Highlight:INSERT SQL集合每列SQL用表格名去撈取對應SQL資料庫欄位屬性做處理,將INSERT SQL集合與SQL資料庫屬性集合做Join
- Question:原本SQL語句只有5句,處理後暴增為17句
?
- Answer:
  - Join首先要考量key會是一對一、一對多、多對多
  - 一對多情況通常情境是紀錄檔對基本檔,屬正常情況
  - 多對多通常就會有大量重複資料,像此種狀況因寫入單據資料(表身都是同張表格名),此種狀態就會變成乘積

2. #flashcards 
- Highlight:MS-SQL預存程序將原本資料計算轉換成產出結果表,INSERT INTO SELECT 
- Question:轉換出來筆數不一致
?
- Answer:因為主表為使用者建檔,有key空白,導致 INNER JOIN 撈取資訊配對不到
   - 直覺將主表改成LEFT JOIN,但是衍生出新的問題,因為所要撈取副表key-value為1-M關係(主表為批覆書表頭、單副表為對應動用批單單身)
   - 衍生出數量變成**乘積**狀態
   - 解決方式:先將副表內key-value 弄成 1-1關係.在透過LEFT JOIN方式也可避免掉數量可能為少情況
   - **INNER JOIN**也是有可能會造成數量乘積特性,若右側數量與左側key配對不是1-1關係情況(批覆書對應動用批單，一張批覆書可能有多張動用批單)
   - 可用主陳述式SELECT (select top 1 column from table) As 欄位將其處理，解決**乘積**狀態

3. #flashcards 
- Highlight:預存程序UPDATE JOIN 所要更新資料
- Question:轉換出來資料會有覆蓋情況
?
- Answer:確保主表JOIN不管幾張副表從頭到尾都必需數量一致，否則更新欄位排序第一列為基準，目前情境為第一張副表為1-1,第二張為1-M
- 但是我要取得第二張副表來進行更新,第一張表只是中介key表格
- 可用子查詢第一與二給處理過後在JOIN主表
- 最後要確認JOIN每個副表都是要1-1情況

4. #flashcards 
- Highlight:
- Question:UPDATE JOIN 怎麼調用都語法錯誤
?
- Answer:
- 也要有FROM As別名
- INNER JOIN內不能有子查詢,需用With
```
With wrnt_underlying_event_date As(
SELECT ROW_NUMBER() Over (PARTITION by wrnt_id ORDER BY event_date DESC) As seq,*
FROM wrnt_underlying
WHERE wrnt_id IN(
SELECT wrnt_id
FROM wrnt_underlying
WHERE event_date > @zDate
GROUP BY wrnt_id)
)
,wrnt_underlying_event_date_1 As (
SELECT * FROM wrnt_underlying_event_date WHERE seq = 1
)
UPDATE wrnt_underlying
SET event_date = @zDate
FROM wrnt_underlying M
INNER JOIN wrnt_underlying_event_date_1 U
ON M.wrnt_id = U.wrnt_id AND M.event_date = U.event_date;
```

5. #flashcards 
- Highlight:徵信報告內財報資訊去撈取對應此徵信報告批覆書內保證人資訊
- Question:發生數量乘積
?
- Answer:可理解乘M-1-1-M，發生乘積算預期之中，應將批覆書表頭與表身先用子查詢給整合成資料集之後再獲取資訊

5. #flashcards 
- Highlight:動用批單額度編號要撈取批覆書額度資訊名稱，因為系統歷史悠久動用批單額度編號欄位有的存取方式為GUID，有的為編碼
- Question:發現JOIN出有沒對應情況，因為資料問題
?
- Answer:透過CASE WHEN 子查詢 THEN來將二種情況都給涵蓋

6. #flashcards 
- Highlight:Oracle中進行LEFT JOIN撈取將主表內顯值，對應編碼表內顯值，衍生在表格投射出外顯值
- Question:ORA-01722: 無效的數字
?
- Answer:二者間JOIN欄位型別並不相同所導致，統一要將其轉成**文字**非數字
```
TO_CHAR(a.data_use_status) = d.CODE_ID
```

7. #flashcards 
- Highlight:要將佣金主檔與其明細刪除
- Question:ORA-02292: 違反完整性限制條件 - 發現子項記錄
?
- Answer:結構明細和主檔有關聯，**順序**刪除明細後才是主檔