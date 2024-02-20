# Metadata
Qty::4
Review::
Restructure::

### Think


# Exception


1. #flashcards 
- Highlight:combobox change to set label，combobox and label是可動態新增
- Question:原本思路為ngFor將label id做計數，但發現html文件 label id無法累加
?
- Answer:解決問題思路要用**綁定**方式，而不是傳統jQuery時代透過DOM操作，直接透過插值語法綁定函數計算即可
```
<label class="col-md-7">{{getlbAddress(j)}}</label>
```

2. #flashcards 
- Highlight:combobox change前面防呆方法檢查目前FormGroup
- Question:是否有類似preventDefault 方法調用?
?
- Answer:preventDefault() 方法通常在需要阻止事件的預設行為時使用，例如在點擊事件中防止超連結的跳轉或按鈕的提交等。對於 change 事件來說，它並沒有一個通用的預設行為需要阻止，因此不需要使用 preventDefault() 方法。無內建preventDefault因此遍歷FormGroup，特別注意當選取combobox當下此資料就已經寫到FormGroup內
```
let selectRepeat = 0;
for(var i=0;i<this.getFormList.length;i++)
        {
            let form = this.getFormList.at(i) as FormGroup;
            if(form.controls["address"].value == valAddress &&
               form.controls["scope"].value == valScope)
            {
                selectRepeat = selectRepeat + 1;
            }
        }
```

3. #flashcards 
- Highlight:將label元件綁定到FormControl上
```
<label class="col-md-7" formControlName="lbAddress2">地址</label>
```
- Question:No value accessor for form control name: 'lbAddress1'
?
- Answer:FormControl只能適用input型標籤元件

4. #flashcards 
- Highlight:按鈕點擊後新增表格上列位，必須將焦點聚焦在新增列位上
- Question:直覺FormControl屬性但無支援
?
- Answer:換另種思路需類似ngOnChange生命周期方式inherit AfterViewInit，再透過click event訂閱
```
@ViewChild('myButton', { static: false }) myButton: ElementRef;
ngAfterViewInit(): void {
        this.renderer.listen(this.myButton.nativeElement, 'click', () => {
          });
}
```

5. #flashcards 
- Highlight:
- Question:
?
- Answer: