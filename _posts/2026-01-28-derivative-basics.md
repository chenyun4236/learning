---
layout: post
title: "高等数学：导数的定义与基本计算"
date: 2024-05-22
categories: [Math]
tags: [导数, 微积分, 极限]
mathjax: true
---

# 导数的定义与基本计算

## 1. 导数的定义

设函数 $f(x)$ 在点 $x_0$ 的某邻域中有定义，当自变量 $x$ 在 $x_0$ 处取得增量 $\Delta x$ 时，函数取得增量 $\Delta y = f(x_0 + \Delta x) - f(x_0)$。

如果极限

$$
f'(x_0) = \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x} = \lim_{\Delta x \to 0} \frac{f(x_0 + \Delta x) - f(x_0)}{\Delta x}
$$

存在，则称函数 $f(x)$ 在点 $x_0$ 处**可导**，该极限值称为 $f(x)$ 在 $x_0$ 处的**导数**。

## 2. 导数的几何意义

导数 $f'(x_0)$ 表示曲线 $y = f(x)$ 在点 $(x_0, f(x_0))$ 处的**切线斜率**。

切线方程：
$$
y - f(x_0) = f'(x_0)(x - x_0)
$$

## 3. 基本求导公式

### 3.1 常数函数
$$
\frac{d}{dx} C = 0 \quad (C为常数)
$$

### 3.2 幂函数
$$
\frac{d}{dx} x^n = nx^{n-1} \quad (n \in \mathbb{R})
$$

### 3.3 指数函数
$$
\frac{d}{dx} e^x = e^x, \quad \frac{d}{dx} a^x = a^x \ln a \ (a>0, a\neq 1)
$$

### 3.4 对数函数
$$
\frac{d}{dx} \ln x = \frac{1}{x}, \quad \frac{d}{dx} \log_a x = \frac{1}{x \ln a}
$$

## 4. 求导法则

### 4.1 线性法则
$$
\frac{d}{dx} [af(x) + bg(x)] = af'(x) + bg'(x)
$$

### 4.2 乘积法则
$$
\frac{d}{dx} [f(x)g(x)] = f'(x)g(x) + f(x)g'(x)
$$

### 4.3 链式法则
$$
\frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x)
$$

## 5. 示例计算

**例1**：求 $f(x) = 3x^2 + 2x - 1$ 的导数。

**解**：
$$
\begin{aligned}
f'(x) &= \frac{d}{dx}(3x^2) + \frac{d}{dx}(2x) - \frac{d}{dx}(1) \\
&= 3 \cdot 2x + 2 \cdot 1 - 0 \\
&= 6x + 2
\end{aligned}
$$

**例2**：求 $f(x) = \sin(3x^2)$ 的导数。

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

导数作为微积分的核心概念，是研究函数变化率的重要工具。掌握基本求导公式和法则是学习后续内容的基础。

---

*下次更新：导数的应用 - 极值问题与函数作图*
