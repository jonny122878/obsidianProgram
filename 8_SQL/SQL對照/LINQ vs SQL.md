
### LINQ與傳統寫法動作視角
|SQL|指令|
|:---|:---|
|Select|廻圈遍歷|
|inner join|雙廻圈|
### LINQ與SQL集合差異視角
- 區分基準，比較。
- C# SQL集合比較基準點相反
- 結構:限制衝突、型態


- 陳述式一定要使用**As**別名
- key配對不用=，用**equals** 
- 投射述句倒置
- from **別名** in **表格** where **條件** select **呈現**
- Zip
  - union, except同SQL
  - 同個集合可按照不同動作ex:union,except做不同的compare物件
  - union在物件元素是用屬性決定ex：二個判定相同物件以主表為主,若只有一張表有此物件，以擁有此物件為主
- Reduce
  - 和SQL主要差別在於因為LINQ每個方法架構本身都**有投射功能**，因此調用時是要建立在Group投射之後再Select投射新的
  - Group投射之後變成原本的集合(要用lambda調用)但是集合的都會增加Key欄位並原本集合按照Key分成多個子集合
  - Group之後出來的集合是原本的集合加上一定會帶有Key屬性需要再用Select去將之轉換
  - LINQ Group By有點是分組而不是移除重復