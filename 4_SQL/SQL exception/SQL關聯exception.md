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

# Unify




1. #flashcards 
- Highlight:MS-SQL預存程序將原本資料計算轉換成產出結果表,INSERT INTO SELECT 
- Question:轉換出來筆數不一致
?
- Answer:因為主表為使用者建檔,有key空白,導致 INNER JOIN 撈取資訊配對不到
   - 直覺將主表改成LEFT JOIN,但是衍生出新的問題,因為所要撈取副表key-value為1-M關係(主表為批覆書表頭、單副表為對應動用批單單身)
   - 衍生出數量變成**乘積**狀態
   - 解決方式:先將副表內key-value 弄成 1-1關係.在透過LEFT JOIN方式也可避免掉數量可能為少情況
   - **INNER JOIN**也是有可能會造成數量乘積特性,若右側數量與左側key配對不是1-1關係情況(批覆書對應動用批單，一張批覆書可能有多張動用批單)
   - 可用主陳述式SELECT (select top 1 column from table) As 欄位將其處理，解決**乘積**狀態

2. #flashcards 
- Highlight:預存程序UPDATE JOIN 所要更新資料
- Question:轉換出來資料會有覆蓋情況
?
- Answer:確保主表JOIN不管幾張副表從頭到尾都必需數量一致，否則更新欄位排序第一列為基準，目前情境為第一張副表為1-1,第二張為1-M
- 但是我要取得第二張副表來進行更新,第一張表只是中介key表格
- 可用子查詢第一與二給處理過後在JOIN主表
- 最後要確認JOIN每個副表都是要1-1情況

3. #flashcards 
- Highlight:在產生Report時將資料UNION整併成各類型項目後呈現
ex: 
```
SELECT '' As 別名
UNION ALL
SELECT '' As 別名
```
- Question:有時會丟出numeric型別錯誤
?
- Answer:情況為需要確保每個子資料集都需要有資料，若其中一個子資料集無資料就會呈現此情況

4. #flashcards 
- Highlight:
- Question:
?
- Answer:

5. #flashcards 
- Highlight:
- Question:
?
- Answer:



# Highlight:
1:
2.
3.
4.徵信報告內財報資訊去撈取對應此徵信報告批覆書內保證人資訊
5.動用批單額度編號要撈取批覆書額度資訊名稱，因為系統歷史悠久動用批單額度編號欄位有的存取方式為GUID，有的為編碼
6. Oracle中進行LEFT JOIN撈取將主表內顯值，對應編碼表內顯值，衍生在表格投射出外顯值
7. 要將佣金主檔與其明細刪除
# Question:
1.
2.
3.
4.發生數量乘積
6. ORA-01722: 無效的數字
7. ORA-02292: 違反完整性限制條件 - 發現子項記錄
# Answer:
1.
2.
3.
4.可理解乘M-1-1-M，發生乘積算預期之中，應將批覆書表頭與表身先用子查詢給整合成資料集之後再獲取資訊
5.透過CASE WHEN 子查詢 THEN來將二種情況都給涵蓋
6. 二者間JOIN欄位型別並不相同所導致，統一要將其轉成**文字**非數字
```
TO_CHAR(a.data_use_status) = d.CODE_ID
```
7. 結構明細和主檔有關聯，**順序**刪除明細後才是主檔