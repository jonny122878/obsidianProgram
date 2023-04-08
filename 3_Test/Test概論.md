# 解決甚麼問題發明
## Integration Test
注重於再不同的**環境**下，都會跑出一樣結果
ex:牽扯IO運作:API、DB、Excel....
- domain object
- valid Data Layer
- Business Layer Logic
## [[Unit Test]]
- 注重limit，若是情境測試極難設定
- 物件相依抽換背後為**LIP**，原本相依物件抽換成固定期望輸出，而不會因相依物件而影響到測試結果
- 原始是相依物件去inherit Sub or Mock Framework而我們去override這個
- [參考](https://medium.com/後端新手村/review-software-testing-anti-patterns-35c9b422dc4e)