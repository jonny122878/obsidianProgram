## 單元測試基本類
- 基本Assert
- 集合CollectionAssert
- 字串StringAssert

## 單元測試準則
- 理論上是按照這個測試類public方法的顆粒度，但在有委派的狀況(因為委派本身就是方法)可以用委派的顆粒度為單位
- 單元測試再測有相依外部的類時候，應該是用抽換原則換上固定的假資料輸出固定的期望值，而不是再測一次
- 易犯錯誤：單元測試再調用時如果是相對路徑那就是以單元測試的路徑而不是測試的路徑
- 相依的抽換主要在外部端調用屬性或方法回傳抽換

###### CollectionAssert
```
using Rhino.Mocks;
var expected = new List<int>();
            expected.AddRange(new[] { 100, 400, 200, 900, 2300, 1900 });
            var actual = new List<int>();
            actual.AddRange(new[] { 100, 400, 200, 900, 2300, 1900 });
            CollectionAssert.AreEqual(expected, actual);
```

###### 相依的抽換
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
