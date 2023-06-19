---
data:
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:


# Highlight:
1. 要將row列內標題和UI元件要放在同列
```
<div class="row">
	<span>員工:</span>
	<input type="number" class="form-control" formControlName="highEmployeeRate" min="0" max="100"/>
</div>
```
2. 要將radioButton和textbox讓其能同列呈現
![[Pasted image 20230617173506.png]]
# Question:
1. 為何用br無法強制換行?
2. 原始思路為透過col-md-12網格，底下在對切網格達到效果
```
        <div class="col-md-12">
            <div class="col-md-6">
                <label class="radio radio-inline">
```
# Answer:
1. 在bootstrap框架下因為已經包覆其內建class row，因此只能用內建class進行網格切版
```
<div class="row">
	<div class="col-md-6">
	</div>
	<div class="col-md-6">
	</div>
</div>
```
2. md-6、row之類class內建都有**margin內縮**，會造成前面無法切齊，目前無解???




