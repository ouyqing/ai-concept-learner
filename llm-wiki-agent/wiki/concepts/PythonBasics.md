---
title: "PythonBasics"
type: concept
tags: [python, basics, variables, types, dynamic-typing]
sources: [python-basics.md]
last_updated: 2026-09-16
---

## 定义
Python 是<strong>动态类型的编程语言</strong>——变量是标签、值是对象，无需提前声明类型。基础语法覆盖 5 种基本类型：int / float / str / bool / None。

## 关键语法
- 变量赋值：`x = 42`、`name = "Alice"`
- 输入：`name = input("提示")`
- 输出：`print(f"你好，{name}")`
- f-string：`f"x 的值是 {x}"`

## 与易混项
- 变量 ≠ 对象：`x = 5` 中 x 是名字贴在整数 5 上
- `==` 在数值上判值等，自定义对象默认判同一性

## 来源
- [Python Basics — Source](sources/python-basics.md)
- [Python Docs: Introduction](https://docs.python.org/3/tutorial/introduction.html)