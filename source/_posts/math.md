---
title: 數學相關
date: 2024-02-25 22:20:31
tags:
description: 數學符號、分數、矩陣
---

# 常用的數學

會用到宏包 `amsmath`
```tex
\usepackage{amsmath}
```


## LaTeX live

[連結](https://www.latexlive.com/##)

它可以將圖片轉為 LaTeX，也有一些基礎的數學式模板，很方便。

## 繁分數

```tex
$\cfrac{\frac{分子}{分母}}{\frac{分子}{分母}}$
```
效果大概會長得像是這樣
$$\cfrac{\frac{分子}{分母}}{\frac{分子}{分母}}$$

## 各種括弧
這邊先以繁分數為例

### 直接打括弧

```tex
$(
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
) $
```
$$(
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
) $$

### 括弧

```tex
$\left(
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
\right) $
```
$$\left(
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
\right) $$

### 中括弧

```tex
$\left[
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
\right] $
```

$$\left[
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
\right] $$

### 大括號

```tex
$\left\{
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
\right\} $
```

$$\left\{
    \cfrac{\frac{7}{6x+11}}{\frac{y^{2}-2xy}{x^{4}+7y}}
\right\} $$

# 矩陣

## 矩陣的括弧

### 前述的括號 + `array`

```tex
\usepackage{array}
$\left|
\begin{array}{cc}
    a & b \\
    c & d
\end{array}
\right|$
```

$$\left|
\begin{array}{cc}
    a & b \\
    c & d
\end{array}
\right|$$

### matrix

```tex
$\begin{matrix}
    a & b \\
    c & d 
\end{matrix}$
```

$$\begin{matrix}
    a & b \\
    c & d \\
\end{matrix}$$

### pmatrix

```tex
$\begin{pmatrix}
     a & b \\
     c & d 
\end{pmatrix}$
```

$$\begin{pmatrix}
     a & b \\
     c & d \\
\end{pmatrix}$$

### bmatrix

```tex
$\begin{bmatrix}
    a & b \\
    c & d
\end{bmatrix}$
```

$$\begin{bmatrix}
    a & b \\
    c & d
\end{bmatrix}$$

### vmatrix

```tex
$\begin{vmatrix}
     a & b \\
     c & d
\end{vmatrix}$
```

$$\begin{vmatrix}
     a & b \\
     c & d
\end{vmatrix}$$

## 矩陣的點點

LaTeX 有符號可以直接用。

```tex
$\ldots \cdots \vdots \ddots$$ %\ldots 和 \dots 效果一致
```

$$\ldots\quad\cdots\quad\vdots\quad\ddots$$

但如果要自己轉點點的話，就要用到宏包 `rotating`

```tex
\usepackage{rotating}
```