# Metadata
Qty::2
Review::
Restructure::

### Think

# Exception


1. #flashcards 
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

2. #flashcards 
- Highlight:
- Question:table能否做到隱藏欄效果
?
- Answer:將table放置在特定div class內即可
```
<div class="table-responsive">
    <table class="table">
      <thead>
        <tr>
          <th class="col-md-6 col-sm-12 d-none d-sm-block">名稱</th>
          <th class="col-md-6 col-sm-12">MAC</th>
        </tr>
      </thead>
      <tbody>
        <tr>
        <td class="col-md-6 col-sm-12 d-none d-sm-block"></td>
          <td class="col-md-6 col-sm-12"></td>
        </tr>
```

3. #flashcards 
- Highlight:
- Question:
?
- Answer:

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