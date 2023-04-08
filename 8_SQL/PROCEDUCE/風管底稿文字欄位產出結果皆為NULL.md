---
data:2023-03-14
aliases:
---
# Metadata
Status:發芽
Source Type:
Source URL:
Project:租貸
Author:
Note Type:
Topics:PROCEDUCE


# Highlight:
PROCEDUCE移轉到MTB01單位是以批覆書,但單張披覆書對應法人會有多個,因此透過CURSOR+UPDATE方式將欄位串接
ex:法人1+法人2....
# Question:
轉出來結果有些欄位明明是對應法人,但其產出NULL
# Answer:
發先原因再於1張批覆書對應3個法人,但是其中**1位法人NULL**,任何型態+NULL=NULL