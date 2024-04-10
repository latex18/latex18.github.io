---
title: 表格相關
date: 2023-12-25 22:22:53
tags:
description: 表格樣式等設定
---

# 表格的框框

`\tabular` 是最常見的形式。
基本的結構如下

```tex
\begin{tabular}[c]{lll}
\hline
column1 & column2 & column3 \\
\hline
item1   & item2   & item3 \\
itemA   & itemB   & itemC \\
\hline
\end{tabular}
```

`[c]` 表示 `center`，其他的還有 `t` 表示 `top`、`b` 表示 `bottom`。
`{lll}` 裡面的 `l` 表 `left`，其他的還有 `r` 表 `right`、`c` 表 `center`。
`|` 表示縱線，雙縱線就寫 `||`。
所以想要項目之間有直線隔開的話就可以寫成 `{|1|1|1|}`。
`\hline` 表示橫線，雙橫線就寫 `\hline\hline`。

# 表格內換行

有時候會遇到表格內文字太多，需要換行的情況。
這個時候就會需要宏包 `makecell`
```tex
\usepackage{makecell}
```

用法會像是
```tex
\makecell[r]{ouo\\OAO\\ouo}
```
這樣，換行只需要用 `\\` 就可以了。

這裡的 `[r]` 跟上面的是一樣的意思，所以同理，也可以替換成 `l` 或 `c` 來表示要讓文字靠左或置中。

# 要給表格加名稱

```tex
\begin{table}[H]
\caption{表格名稱}
\centering
\begin{tabular}{llll}
...
\end{tabular}
\end{table}
```
這樣就好了
`[H]` 代表這個表格的位置要在我下指令的地方，其他的還有 `t` 表示在頁面頂端、`b` 表示在底端、`p` 表示單獨佔一頁。
`\caption` 就是它的名稱，編譯後會是 `Table n. 表格名稱` 這個樣子，通常來說會放在表格的上面。
`\centering` 則是表示要讓表格置中。
