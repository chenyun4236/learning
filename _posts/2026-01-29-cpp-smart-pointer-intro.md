---
title: C++ 智能指针基础梳理
date: 2026-01-29
categories:
  - cpp
---

## 一、为什么需要智能指针

在 C++ 中，手动 `new/delete` 容易导致：

- 内存泄漏
- 重复释放
- 异常安全问题

智能指针通过 **RAII** 思想解决这些问题。

## 二、unique_ptr

```cpp
#include <memory>

std::unique_ptr<int> p = std::make_unique<int>(10);
