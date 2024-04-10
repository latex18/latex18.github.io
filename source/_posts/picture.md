---
title: 圖片相關
date: 2023-12-27 22:27:41
tags:
description: 插入圖片、pdf
---

# 放置圖片

我們會需要使用到宏包 `graphicx`
```tex
\usepackage{graphicx}
```
在插入圖片的時候，最簡單的用法就會像是這樣

```tex
\includegraphics[width=15cm]{圖片名稱}
```

`width = 15cm` 是讓圖片等比例縮放至寬為 15 公分，所以也可以改成其他的長度。

# 給圖片加個名稱

```tex
\begin{figure}[H]
    \centering
    \includegraphics[width=15cm]{圖片位置}
    \caption{圖片}
\end{figure}
```

`[H]` 代表圖片的位置要在我下指令的地方，其他的還有 `t` 表示在頁面頂端、`b` 表示在底端、`p` 表示單獨佔一頁。
`\caption` 就是它的名稱，編譯後會是 `Figure n. 圖片` 這個樣子，通常來說會放在圖片的下面。
`\centering` 則是表示要讓圖片置中。
圖片位置可以用路徑表示，也可以直接把他放在跟 .tex 檔同個目錄下。

# 插入 pdf

如果 pdf 有很多頁的話，我們可以使用宏包 `pdfpages`。
```tex
\usepackage{pdfpages}
```

用法會像是
```tex
\includepdf[pages={特定頁數}]{pdf檔案.pdf}
```
特定頁數的區隔要用 `,` 隔開，如果是整份文章都需要的話，`[pages={-}]` 這樣就好了。