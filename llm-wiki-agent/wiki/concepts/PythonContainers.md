---
title: "PythonContainers"
type: concept
tags: [python, containers, list, tuple, dict, set]
sources: [python-containers.md]
last_updated: 2026-09-16
---

## 定义
Python 提供四类内置容器：<strong>list（可变长队列）/ tuple（只读队列）/ dict（键值对）/ set（去重桶）</strong>。选错容器效率差 100 倍。

## 对比
| 类型 | 语法 | 可变 | 有序 | 典型用途 |
|------|------|------|------|----------|
| list | [1,2,3] | ✓ | ✓ | 动态数组 |
| tuple | (1,2,3) | ✗ | ✓ | 不可变记录 |
| dict | {'a':1} | ✓ | 插入序 | 键值查找 |
| set | {1,2,3} | ✓ | ✗ | 去重、集合运算 |

## 性能要点
- list 查找 O(n)
- dict/set 查找 O(1)
- 判断"某元素是否在容器中"，用 set/dict 更快

## 来源
- [Python Containers — Source](sources/python-containers.md)
- [Python Docs: Data Structures](https://docs.python.org/3/tutorial/datastructures.html)