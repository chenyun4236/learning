---
layout: post
title: "导数的定义与计算方法"
date: 2024-02-02
categories: [高等数学]
tags: [导数, 微积分, 极限]
mathjax: true  # 启用公式渲染
---

# 导数的定义

## 定义
设函数 $f(x)$ 在点 $x_0$ 的某邻域中有定义，
记 $\Delta x = x - x_0$，$\Delta y = f(x) - f(x_0)$，分别为自变量与函数的增量。

若极限

$$
\lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x} = \lim_{\Delta x \to 0} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x} = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0}
$$

存在，则称此极限为函数 $y = f(x)$ 在 $x_0$ 处的**导数**或**微商**，
记为 $f'(x_0)$ 或 $\left. \frac{dy}{dx} \right|_{x=x_0}$，此时称函数 $f(x)$ 在 $x_0$ 处**可导**。

---

## 定义
设函数 $f(x)$ 在开区间 $(a, b)$ 上点点可导，
则称 $f(x)$ 在 $(a, b)$ 上可导，记作 $f(x) \in D(a, b)$，
此时有**导函数** $f'(x)$ 或 $\frac{dy}{dx}$。通常，导函数亦简称为**导数**。

---

## 几何意义

导数的几何意义是曲线 $y = f(x)$ 在点 $(x_0, f(x_0))$ 处的**切线斜率**。

设曲线 $y = f(x)$ 在点 $P(x_0, y_0)$ 处可导，则切线方程为：

$$
y - y_0 = f'(x_0)(x - x_0)
$$

---

## 基本求导公式

### 1. 常数函数
$$
\frac{d}{dx} C = 0 \quad (C \text{为常数})
$$

### 2. 幂函数
$$
\frac{d}{dx} x^n = nx^{n-1} \quad (n \in \mathbb{R})
$$

### 3. 指数函数
$$
\frac{d}{dx} e^x = e^x, \quad \frac{d}{dx} a^x = a^x \ln a \quad (a > 0, a \neq 1)
$$

### 4. 对数函数
$$
\frac{d}{dx} \ln x = \frac{1}{x}, \quad \frac{d}{dx} \log_a x = \frac{1}{x \ln a}
$$

### 5. 三角函数
$$
\begin{aligned}
\frac{d}{dx} \sin x &= \cos x \\
\frac{d}{dx} \cos x &= -\sin x \\
\frac{d}{dx} \tan x &= \sec^2 x \\
\frac{d}{dx} \cot x &= -\csc^2 x
\end{aligned}
$$

---

## 求导法则

### 1. 线性法则
$$
\frac{d}{dx} [af(x) + bg(x)] = af'(x) + bg'(x)
$$

### 2. 乘积法则
$$
\frac{d}{dx} [f(x)g(x)] = f'(x)g(x) + f(x)g'(x)
$$

### 3. 商法则
$$
\frac{d}{dx} \left[ \frac{f(x)}{g(x)} \right] = \frac{f'(x)g(x) - f(x)g'(x)}{[g(x)]^2}, \quad g(x) \neq 0
$$

### 4. 链式法则
$$
\frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x)
$$

---

## 高阶导数

函数 $y = f(x)$ 的导数 $f'(x)$ 的导数称为**二阶导数**，记作：

$$
f''(x) = \frac{d}{dx} f'(x) = \frac{d^2 y}{dx^2}
$$

类似地，可以定义 $n$ 阶导数：

$$
f^{(n)}(x) = \frac{d^n y}{dx^n}
$$

---

## 示例

### 示例1：求 $f(x) = 3x^2 + 2x - 1$ 的导数
**解**：
$$
\begin{aligned}
f'(x) &= \frac{d}{dx}(3x^2) + \frac{d}{dx}(2x) - \frac{d}{dx}(1) \\
&= 3 \cdot 2x^{2-1} + 2 \cdot 1 - 0 \\
&= 6x + 2
\end{aligned}
$$

### 示例2：求 $f(x) = \sin(3x^2)$ 的导数
**解**（使用链式法则）：
$$
\begin{aligned}
f'(x) &= \cos(3x^2) \cdot \frac{d}{dx}(3x^2) \\
&= \cos(3x^2) \cdot 6x \\
&= 6x \cos(3x^2)
\end{aligned}
$$

---

## 总结

| 概念 | 记号 | 定义 |
|------|------|------|
| 导数 | $f'(x_0)$ | $\lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x}$ |
| 可导 | $f(x) \in D(I)$ | 在区间 $I$ 上每点可导 |
| 导函数 | $f'(x)$ | 导数的函数形式 |
| 微分 | $dy$ | $dy = f'(x)dx$ |

---

## 参考文献
1. 《高等数学》（同济大学第七版）
2. 《微积分学教程》（菲赫金哥尔茨）

---

*注意：本文使用 MathJax 渲染数学公式，请确保浏览器支持 JavaScript。*
