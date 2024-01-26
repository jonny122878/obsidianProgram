# Metadata
Status::發芽
Source Type::工作
Source URL::
Project::金財通
Author::
Note Type::
Topics::
Qty::5
Review::
Restructure::

#work #知識 
# Unify
- 情境測試應用情境在SIT、UAT 參數都設定相同
- 注重limit，若是情境測試極難設定
- 物件相依抽換背後為**LIP**，原本相依物件抽換成固定期望輸出，而不會因相依物件而影響到測試結果
- [參考](https://medium.com/後端新手村/review-software-testing-anti-patterns-35c9b422dc4e)
# Exception


1. #flashcards 
- Highlight:
- Question:Integration Test準則3項
?
- Answer:
注重於再不同的**環境**下，都會跑出一樣結果
ex:牽扯IO運作:API、DB、Excel....
- domain object
- valid Data Layer
- Business Layer Logic


2. #flashcards 
- Highlight:
- Question:Unit Test準則5項
?
- Answer:
- 原始是相依物件去inherit Sub or Mock Framework而我們去override這個
- 理論上是按照這個測試類public方法的顆粒度，但在有委派的狀況(因為委派本身就是方法)可以用委派的顆粒度為單位
- 單元測試再測有相依外部的類時候，應該是用抽換原則換上固定的假資料輸出固定的期望值，而不是再測一次
- 易犯錯誤：單元測試再調用時如果是相對路徑那就是以單元測試的路徑而不是測試的路徑
- 相依的抽換主要在外部端調用屬性或方法回傳抽換


3. #flashcards 
- Highlight:C
- Question:測試類案例
?
- Answer:
- 基本Assert
- 集合CollectionAssert
- 字串StringAssert


4. #flashcards 
- Highlight:
- Question:CollectionAssert 集合測試範例
?
- Answer:
```
using Rhino.Mocks;
var expected = new List<int>();
            expected.AddRange(new[] { 100, 400, 200, 900, 2300, 1900 });
            var actual = new List<int>();
            actual.AddRange(new[] { 100, 400, 200, 900, 2300, 1900 });
            CollectionAssert.AreEqual(expected, actual);
```

5. #flashcards 
- Highlight:
- Question:MockRepository 相依抽換範例
?
- Answer:
```
using Rhino.Mocks;
[TestMethod]
        public void TestMaxbackWidthByGrid()
        {
            var expected = 10000;
            var inputWidths = new List<int> { 600, 1600, 1600, 1280, 700 };
            var testGrid = MockRepository.GenerateStub<DataGridView>();
            testGrid.Size = new System.Drawing.Size(expected, expected);
            //testGrid.Stub(x => x.Size.Width).Return(2000);

            var target = new CountPercentByGrid(testGrid);
            var results = target.GetResults(inputWidths);
            Assert.AreEqual(expected, results.Sum());

        }
```

6. #flashcards 
- Highlight:
- Question:
?
- Answer:

