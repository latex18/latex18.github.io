---
title: 一些簡單的設定
date: 2024-02-09 19:42:01
tags:
description: 語言、版面、中文排版相關的設定。
---

# 語言設定

要利用中文進行編輯的話，需要先將 compiler 設為 `XeLaTeX`
然後添加

```tex
\usepackage{xeCJK}
```

# 版面設定

版面設定有兩個方法，可以直接放在 `\documentclass` 之後，也可以用 `geometry` 這個宏包進行設定

```tex
\documentclass[a4paper, 10pt]{article}
```

```tex
\documentclass{article}
\usepackage[paperwidth=50cm, paperheight=50cm]{geometry}
```

```tex
\documentclass{article} 
\usepackage[a5paper]{geometry}
```

假設今天需要橫的 a4 紙的話，可以利用 `landscape` 進行設定

```tex
\documentclass[a4paper, landscape]{article}
```

# 自動換行與中文段落首句空兩格

雖然在 LaTeX 中用 `\\` 或是空一行就可以讓段落的段首空兩格，但是首段因為它會認為是引言，不會空格。
在文中使用 identfirst 就可以解決這個問題了
```tex
\usepackage{indentfirst}
```
```tex
\setlength{\parindent}{2em}
```
可以控制縮進的大小。2em 就是縮進兩個字符的意思。

```tex
\XeTeXlinebreaklocale "zh"
\XeTeXlinebreakskip = 0pt plus 1pt
\usepackage{indentfirst} 
\setlength\parindent{2em}
\usepackage{setspace}
```
上面這個加下去空一行就會自動判定成不同的段落，就不需要再在末尾加上 `\\` 了。

# 行距設定

像是科展有要求要 1.5 倍行距。
所以就可以利用
```tex
\linespread{1.5}
```
來實現，其他也是同理。

# 項目符號自定義

`\section{}` 代表的是一個章節的標題，項目符號自定義就是在講說如何讓你的標題長得像是你想要的樣子（像是粗體、斜體、底線之類的）

首先我們要使用宏包

```tex
\usepackage{titlesec}
\usepackage{titletoc}
```
```tex
\titleformat{\section}[hang]{\centering\bfseries\Large}{}{0pt}{}[]
```
這樣就可以用了
上面的 `\centering` 是置中
`\bfseries` 是指粗體，`\Large` 則是字體的大小。

如果是需要項目縮排的話
```tex
\titlespacing{\subsubsection} {2em}{0em}{0em}
```
可以用 `titlespacing` 的指令，向上面這樣就是讓 `\subsubsection` 的標題往前兩個字符的大小。