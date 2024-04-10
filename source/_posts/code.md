---
title: 程式碼相關
date: 2024-02-27 22:24:06
tags:
description: 程式碼相關設定
---

# 插入程式碼

需要用到宏包 `listing`。 
```tex
\usepackage{listing}
```

## 基礎外觀設定

```tex
\lstset{
    basicstyle = \ttfamily,
    rulesepcolor = \color{black},
    breaklines = true,
    numbers = left, 
    numberstyle = \small,
    keywordstyle = \color{blue},
    commentstyle = \color{gray},
    aboveskip = 3mm,
    belowskip = 3mm
}
```
東西都要包在 `lstset` 裡面。
`basicstyle` 的 `\ttfamily` 是指等寬字體。
其他的這裡就不多加贅述。

## 輸入程式碼

用 `lstlisting`，具體如下

```tex
\begin{lstlisting}
#include<iostream>
using namespace std;

int main()
{
    cout << "hello, world" << '\n';
    return 0;
}
\end{lstlisting}
```