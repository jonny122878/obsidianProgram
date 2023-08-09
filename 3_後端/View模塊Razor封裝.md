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
Topics::
#資訊 

# Unify
- 依循DIP和層次概念，每個先由高層次到低層次版型=>區塊=>元件
- 生命週期為Layout先進入，再一層層剝洋蔥式的進到內核的View

# 版型
Layout部分區分為單層和巢狀嵌套。
# 區塊
區塊主打的部分會因其不同的需求而有不同的主打抽象，最常用的是HelperResult，以及只有單一頁面的業務邏輯PartialView，和型別上的變化Template。
# 元件
元件主要是將共用的參數再進行提鍊，分為基底為Helper再進行封裝或是常用的HTML。
