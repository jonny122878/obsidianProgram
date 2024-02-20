
2. #flashcards 
- Highlight:Oracle
- Question:SELECT TOP 1
?
- Answer:
```
SELECT BRANCHCODE,Flag FROM COMMON_ORGANIZATION FETCH FIRST 1 ROWS ONLY
```

5. #flashcards 
- Highlight:typescript
- Question:splice使用時機
?
- Answer:其有點類似take、skip之類放置where參數指定索引與長度
```
// 删除元素示例 
const deletedElements = array.splice(2, 2); 
console.log(array); // 输出: [1, 2, 5] 
console.log(deletedElements); // 输出: [3, 4]
```

1. #flashcards 
- Highlight:javascript
- Question:如何將IEnumerable轉成array
?
- Answer:ToArray: Array.prototype.slice.call(**IEnumerable**) 


### 計算前幾季平均,補缺失值
- 將時間的基本檔撈取出
- 將商品基本檔撈取出
- 時間和商品CROSS JOIN出主表
- 主表再去LEFT JOIN消除NULL值
- ROW_NUMBER()弄出order scale欄位，支援前幾、後幾平均