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
Qty::5
#知識  #work 
# Unify
- 轉型函數設計通常會按照來源型別區分，ex:字串、布林
- 特殊型別除了Number都無法成功轉型，差別再於強弱型別呈現方式不同
- Number因其吃布林，checkbox UI很適用轉換


1. #flashcards 
- Highlight:C#
- Question:Convert與TryPrase區別
?
- Answer:
應盡量用TryPrase
```
decimal d=0;
decimal.TryPrase("str",out d);
```

好處在於不會丟**exception**,並且能數字格式字串ex:序號001，千分位1,000
int.TryPrase也有類似效果


2. #flashcards 
- Highlight:TypeScript
- Question:parseInt轉出NaN型別
?
- Answer:吃入null、空字元、undefined、布林字串true

3. #flashcards 
- Highlight:TypeScript
- Question:parseInt能否直接吃數字格式字串ex:序號001，千分位1,000
?
- Answer:序號無異常，吃千分位會有**截斷**現象，產出1結果

4. #flashcards 
- Highlight:C#
- Question:已經調用Math.Round,但為何結果小數位數不如預期
?
- Answer:預設為**四捨六入**,須設定參數MidpointRounding.AwayFromZero


5. #flashcards 
- Highlight:TypeScript
- Question:Number、parseInt 
?
- Answer:parseInt能各種字串，Number擅長能非字串，吃布林型別、null、空字元都會當成0





6. #flashcards 
- Highlight:
- Question:
?
- Answer:

