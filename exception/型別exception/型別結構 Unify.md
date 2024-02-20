# Metadata
Qty::4
Review::
Restructure::unify

### Think


# Exception


1. #flashcards 
- Highlight:
- Question:型別本身會有疊加態，在數字上呈現2種特性
?
- Answer:
- 流水號是額外擴充寫入資料誤區
	[[cvt num SQL exception]]2.、4.
- 數字規範衍生出寬鬆轉嚴謹紀錄小數位相關規範
	[[cvt num exception]]3.
	[[cvt num SQL exception]]1.、3.、5.
	
2. #flashcards 
- Highlight:
- Question:型別本身會有疊加態，在字串上呈現3種特性
?
- Answer:
- 編碼不同衍生衝突
	[[string SQL exception]]2.
	[[string exception]]1.
- 所佔byte不同衍生資料庫定序，衍生出集合結合操作
	[[string SQL exception]]4.、5.
- ntext、varbinary(max)因過長已經跳脫出平常string能運算範圍，衍生出集合結合操作
	[[string SQL exception]]1.、3.

3. #flashcards 
- Highlight:
- Question:null和其他型別運算3種結果
?
- Answer:
- 丟exception
- 數字和null四則運算，字串和null相加不丟exception
	[[null exception]]2.、3.、5.
	[[null SQL exception]]1.
- 丟出特殊型別

4. #flashcards 
- Highlight:
- Question:日期型別結構定義衍生2種特性
?
- Answer:
- 日期儲存字串日期格式表示
	[[cvt date SQL exception]]1.
	[[cvt date exception]]3.、4.
- 日期運算無語法糖要特定函數
	[[cvt date SQL exception]]2.
	
5. #flashcards 
- Highlight:
- Question:弱型別類似interface和class階層關係，能給其他實作，衍生二種特性
?
- Answer:
- object本身不屬於任何實作不能用extension method
- 弱型別權限作用子較大，model.ts型別註記只在IDE有效，若是接收any會被override

6. #flashcards 
- Highlight:
- Question:物件本質為參考型別，
?
- Answer:


- declare function給其他component調用時要注意物件參考特性
- 
- 物件delcare方式C#與typescript不同，typescript並不會自行將屬性給定義


- Boolean特別適用數字model 轉UI checkbox，但須小心Number(100) = true誤區
	[[cvt bool exception]]
