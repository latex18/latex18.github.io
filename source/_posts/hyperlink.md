---
title: 連結
date: 2024-03-27 22:28:33
tags: 
description: 超連結、文內超連結設定
---

# 超連結
如果要使用超連結的話要用宏包 `hyperref`

使用方式可以像這樣

```tex
\usepackage[colorlinks, linkcolor=red]{hyperref}
```

linkcolor 可以改成其他顏色，這樣你的超連結就會是不同顏色的。

要引用超連結的話就像這樣直接用就好了

```tex
\url{https://hackmd.io/?nav=overview}
```

但如果這樣的話會發現超連結並不會自動換行。
所以加上
```tex
\makeatletter
\def\UrlAlphabet{%
      \do\a\do\b\do\c\do\d\do\e\do\f\do\g\do\h\do\i\do\j%
      \do\k\do\l\do\m\do\n\do\o\do\p\do\q\do\r\do\s\do\t%
      \do\u\do\v\do\w\do\x\do\y\do\z\do\A\do\B\do\C\do\D%
      \do\E\do\F\do\G\do\H\do\I\do\J\do\K\do\L\do\M\do\N%
      \do\O\do\P\do\Q\do\R\do\S\do\T\do\U\do\V\do\W\do\X%
      \do\Y\do\Z}
\def\UrlDigits{\do\1\do\2\do\3\do\4\do\5\do\6\do\7\do\8\do\9\do\0}
\g@addto@macro{\UrlBreaks}{\UrlOrds}
\g@addto@macro{\UrlBreaks}{\UrlAlphabet}
\g@addto@macro{\UrlBreaks}{\UrlDigits}
\makeatother
```
這樣就好了

# 文內超連結

首先，你在寫文章的時候就要設置 `\label`
具體可能會像是這樣

```tex
\section{Chapter 1}
\label{ch1}
```
那這樣這個標籤就會是 Chapter 1 的標籤。
之後你要引用 Chapter 1 的話，就可以用 `\ref`

```tex
\ref{ch1}
```
像這樣就可以用了！
但要注意一個點是
假設 Chapter 1 是第一大點的話，那 `\ref{ch1}` 出來的就會是 `1`，而非 `Chapter 1`
同理，如果 Chapter 1 是第一大點的第一小點的話，`\ref{ch1}` 就會是 `1.1`

如果你的 `\label` 是要放在圖片或是表格的話，要記得放在 `\caption` 的後面。