# Metadata
Qty::4
Review::
Restructure::question 1

### Think


# Unify




1. #flashcards 
- Highlight:要將radioButton和textbox讓其能同列呈現
![[Pasted image 20230617173506.png]]
- Question:原始思路為透過col-md-12網格，底下在對切網格達到效果
```
        <div class="col-md-12">
            <div class="col-md-6">
                <label class="radio radio-inline">
            <div class="col-md-6">
```
?
- Answer:md-6、row之類class內建都有**margin內縮**，會造成前面無法切齊，目前無解???

2. #flashcards 
- Highlight:
![[Pasted image 20230627183006.png]]
- Question:想要達到靠左，但發現其靠右
?
- Answer:control-label 排版靠右

3. #flashcards 
- Highlight:
- Question:文字框如何達到二個文字框同列效果
?
- Answer:form-control具有display:block

4. #flashcards 
- Highlight:
- Question:form-horizontal選用職責
?
- Answer:水平表单布局通过将标签（label）和表单控件（form control）放置在同一行来实现，这种布局方式使得标签和表单控件在同一行上对齐


9. #flashcards 
- Highlight:
- Question:
?
- Answer:

