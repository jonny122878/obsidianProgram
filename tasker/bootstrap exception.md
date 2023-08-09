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
Topics::前端
#資訊 #work 
# Unify




1. #flashcards 
- Highlight:要將row列內標題和UI元件要放在同列
```
<div class="row">
	<span>員工:</span>
	<input type="number" class="form-control" formControlName="highEmployeeRate" min="0" max="100"/>
</div>
```
- Question:為何用br無法強制換行?
?
- Answer:在bootstrap框架下因為已經包覆其內建class row，因此只能用內建class進行網格切版、可讓內部div預設換行從區塊變成行內
```
<div class="row">
	<div class="col-md-6">
	</div>
	<div class="col-md-6">
	</div>
</div>
```

2. #flashcards 
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

3. #flashcards 
- Highlight:
![[Pasted image 20230627183006.png]]
- Question:想要達到靠左，但發現其靠右
?
- Answer:control-label 排版靠右


4. #flashcards 
- Highlight:
- Question:文字框如何達到二個文字框同列效果
?
- Answer:form-control具有display:block

5. #flashcards 
- Highlight:
- Question:在表單列右側輸入元件特別長，該如何縮小
?
- Answer:調整col-md-11，其會轉譯成width百分比


6. #flashcards 
- Highlight:
- Question:form-horizontal選用職責
?
- Answer:水平表单布局通过将标签（label）和表单控件（form control）放置在同一行来实现，这种布局方式使得标签和表单控件在同一行上对齐

7. #flashcards 
- Highlight:bootstrap切版頁籤
```
<li>
<a (click)="changeTab(tabEnum.ThirdRentLossCal)">BI\第三人\租金損失 試算</a>
</li>
<tab [active]="tab==tabEnum.Main"
(click)="refreshretAddressQueryLists">
</tab>
```
- Question:為何click頁籤並無trigger對應click event
?
- Answer:直覺理解錯誤，html上方頁籤應是li

8. #flashcards 
- Highlight:
- Question:
?
- Answer:

