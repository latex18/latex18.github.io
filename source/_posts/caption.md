---
title: 圖片與表格設定
date: 2024-04-10 14:17:24
tags: 
description: 圖片和表格的名稱設定、圖片和表格並排放等...
---

# 圖片和表格的名稱設定

有時候會遇到規定說圖片的標題要是 `圖 n 圖片名稱` 這樣的。
或是我們不想要前面的 `Figure`。
那我們可以在前面加上
```tex
\renewcommand{\figurename}{圖}
```
可以把 `Figure` 改成 `圖`

```tex
\caption*{圖片名稱}
```
則是會讓圖題名稱不見。

```tex
\renewcommand{\captionlabeldelim}{.~}
```
會重新定義分隔號。

# 圖片和表格並排放

我們要用到 `minipage`。
用 `minipage` 將頁面分成兩塊，一邊放圖，一邊放表格。

```tex
 \begin{figure}[H]
    \centering
    \begin{minipage}[H]{0.48\textwidth}
        \begin{table}[H]
            \centering
            \caption{表格名稱}
            \begin{tabular}{cc}
                ...
            \end{tabular}
        \end{table}
    \end{minipage}
    \begin{minipage}[H]{0.48\textwidth}
        \centering
        \includegraphics[width = 7cm]{圖片}
        \caption{圖片名稱}
    \end{minipage}
\end{figure}
```
圖片和圖片並排或是表格與表格並排皆同理。