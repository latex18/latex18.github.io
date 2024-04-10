---
title: 字型設定
date: 2024-01-26 22:18:09
tags:
description: 字體、文字顏色等設定
---

# 字體設定

## 內建字體
如果是用 [Overleaf](https://www.overleaf.com/)，他是有內建字體的。
可以參考[這裡](https://www.overleaf.com/learn/latex/Questions/Which_OTF_or_TTF_fonts_are_supported_via_fontspec%3F)

使用上就像是

```tex
\setCJKmainfont{Noto Serif CJK TC}
```

## 非內建字體
如果是用 vscode 進行編輯或者是想要的字體不在 Overleaf 內建選項裡面的話。
可以先自行上網把 ttc 或是 otc 檔下載下來。
然後再用

```tex
\usepackage{fontspec}
\setCJKmainfont{mingliu.ttc}
```

`\setmainfont` 有點像是設置默認字體，而 `\setCJKmainfont` 是設置中文字體的。

如果你會用到粗體或是斜體而且你有檔案的話，利用

```tex
\setCJKmainfont[BoldFont=NotoSerifTC-Bold.otf]{NotoSerifTC-Medium.otf} 
```

可以設置粗體或是斜體。
這裡是設置粗體，那如果要斜體的話，`BoldFont` 要換成 `SlantFont`。

但是如果你沒有檔案的話，其實最簡單也最快的方法就是用

```tex
\setCJKmainfont[AutoFakeBold = 3]{mingliu.ttc}
```

如果是斜體的話就是 `AutoFakeSlant`。
`=` 後面的數字可以任意改，改一個看得順眼的數字就好了，但印象中小於 1 就好了。

# 改變字的顏色

需要用到宏包 `color`。
```tex
\usepackage{color}
```

如果是要 xcolor 預設的顏色關鍵字的話，可以從[這裡](https://ctan.mirror.twds.com.tw/tex-archive/macros/latex/contrib/xcolor/xcolor.pdf#section.4)找到。

## 方法一

```tex
\textcolor{顏色}{文字}
```
顏色可以填系統定義好的顏色

## 方法二

```tex
textcolor[rgb]{數值, 數值, 數值}{文字}
```

LaTeX 中 rgb 輸入的值為 0~1，所以找到想要的顏色對照的 rgb 號碼之後記得除以 255 再打進去。
色碼可以去[這裡](https://www.ginifab.com.tw/tools/colors/color_picker_from_image.php#google_vignette)找。

## 方法三

```tex
textcolor[RGB]{數值, 數值, 數值}{文字}
```
跟 rgb 不同，RGB 輸入的值可以是 0 ~ 255