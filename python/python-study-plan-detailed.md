# Python 基础语法四次课教学方案

> 目标：用 4 次课（每次上/下两节 45 分钟，共 6 小时）把 Python 基础语法学完，
> 并在第 4 课结束前自然过渡到 `statistics` / `NumPy` / `pandas`，为后续统计分析铺路。
> 教学环境：VS Code + Python 3.12+ 扩展 + 终端运行。

---

## 总体结构一览

| 课次 | 主题 | 上半场 45' | 下半场 45' | 课后小练 |
| --- | --- | --- | --- | --- |
| L1 | 环境与语法骨架 | 装环境、第一个程序、变量、5 种基础类型 | 运算符、if 分支、缩进与注释 | 温度转换器 |
| L2 | 容器与循环 | list / tuple / dict / set、索引切片 | for / while、break/continue、列表推导式 | 成绩统计器 |
| L3 | 函数、模块、文件 | 函数定义与参数、作用域 LEGB、lambda | 标准库、文件读写、异常处理 try/except | CSV 读取清洗 |
| L4 | OOP 与统计分析衔接 | 类与对象、继承、魔术方法 | pip / venv、NumPy、pandas、statistics、matplotlib | 描述统计迷你案例 |

每节 45 分钟节奏：5' 复习 → 25' 新概念 + 演示 → 10' 课堂练习 → 5' 答疑。

---

## 第 1 课 · 环境与语法骨架

**学习目标**：能在 VS Code 里写、跑、改 Python 程序，认识所有基础数据类型，能写条件判断。

### 上半场 45 分钟 — 让 Python 跑起来

1. **环境搭建（10'）**
   - 安装 Python 3.12+，勾选 *Add to PATH*
   - VS Code 安装扩展：`Python`、`Pylance`、`Code Runner`（可选）
   - 选工作区 → `Ctrl+Shift+P` → `Python: Select Interpreter`
   - 终端运行：`python --version`、建一个 `hello.py`

2. **第一个程序 + 变量（10'）**
   ```python
   print("Hello, statistics!")
   name = "Tom"
   age = 25
   pi = 3.14159
   is_student = True
   ```

3. **五种基础类型（15'）**
   - `int` 整数、`float` 浮点
   - `str` 字符串（单/双/三引号、转义 `\n`、`r"..."` 原样输出）
   - `bool` 布尔（注意首字母大写 `True/False`）
   - `NoneType` 空值 `None`
   - `type(x)` 查看类型；`isinstance(x, int)` 判断

4. **I/O 入门（10'）**
   - `print()` 多参数 `sep`、`end`
   - f-string：`f"name={name}, age={age}"`
   - `input("提示:")` 永远返回字符串 → `int(input())` 转换

### 下半场 45 分钟 — 运算符与分支

5. **运算符（15'）**
   - 算术：`+ - * / // % **`（注意 `/` 一定得到 float）
   - 比较：`== != > < >= <=` → 产出 `bool`
   - 逻辑：`and or not`（短路求值）
   - 赋值：`= += -= *= //=`
   - 成员：`in / not in`（先在 L2 容器里展开）

6. **条件分支（20'）**
   - `if / elif / else` 与 4 空格缩进（强制语法）
   - 嵌套分支、`pass` 占位
   - 三元表达式：`score = "pass" if x >= 60 else "fail"`
   - 实战示例：根据 BMI 输出体型

7. **注释与代码风格（5'）**
   - 单行 `#`、多行 `"""..."""`
   - PEP 8 简介：变量 `snake_case`、常量 `UPPER_SNAKE`

8. **L1 课后练习：温度转换器**
   - 读入摄氏温度，输出华氏、绝对温度，异常输入时提示重输

---

## 第 2 课 · 容器与循环

**学习目标**：能处理一组数据，会用循环批量操作，理解推导式。

### 上半场 45 分钟 — 四大容器

1. **复习 & 列表 list（10'）**
   - 创建、索引（负数从右数）、切片 `[start:stop:step]`
   - 增删改：`append / extend / insert / pop / remove / clear`
   - 常用：`len / sorted / min / max / sum`

2. **元组 tuple 与 不可变（5'）**
   - 与 list 的区别；解包 `a, b, c = (1, 2, 3)`

3. **字典 dict（15'）**
   - 键值对；增删改查：`d[k] / d.get(k, default) / d.keys() / d.values() / d.items()`
   - 嵌套 dict（提前为后续 JSON / DataFrame 做铺垫）
   - `dict comprehension`：`{k: v*2 for k, v in d.items()}`

4. **集合 set（10'）**
   - 去重；`& | - ^` 交并差
   - 适用场景：成员判断 / 去重

5. **小演示（5'）**：用 list 存 5 个学生成绩 → 算平均、最高分、按分数排序

### 下半场 45 分钟 — 循环

6. **for 循环（15'）**
   - `for x in iterable:`、`range(start, stop, step)`
   - `enumerate()` 同时拿索引和值
   - `zip()` 并行遍历两个序列
   - 实战：遍历 dict.items() 输出键值

7. **while 循环（10'）**
   - 计数循环、哨兵循环（读到 quit 退出）
   - `break / continue / pass / else`（循环完整跑完才走 `else`）

8. **列表推导式（15'）**
   - 基础：`[x*x for x in range(10)]`
   - 过滤：`[x for x in xs if x > 0]`
   - 嵌套：`[(x, y) for x in xs for y in ys]`
   - dict / set 推导式

9. **L2 课后练习：成绩统计器**
   - 输入若干学生成绩（输入 -1 结束），输出：人数、平均、最高、及格率、按分数降序

---

## 第 3 课 · 函数、模块、文件

**学习目标**：把重复逻辑抽成函数，会用标准库，能读写文件，能处理异常。

### 上半场 45 分钟 — 函数

1. **定义函数（10'）**
   ```python
   def greet(name: str, greeting: str = "Hi") -> str:
       return f"{greeting}, {name}!"
   ```
   - 参数类型与返回值可加注解（提示用，不强制）

2. **参数类型（15'）**
   - 位置参数 / 关键字参数
   - 默认值（注意 mutable 默认值的坑）
   - `*args` 收集多余位置 → tuple
   - `**kwargs` 收集多余关键字 → dict
   - 仅关键字参数 `def f(a, *, key)`、仅位置参数 `def f(a, /)`

3. **作用域 LEGB（10'）**
   - Local → Enclosing → Global → Built-in
   - `global` / `nonlocal`
   - 演示一个闭包示例

4. **lambda 与高阶函数（10'）**
   - `lambda x: x*2`
   - `map / filter / sorted(..., key=)`、`functools.reduce`

### 下半场 45 分钟 — 模块与文件

5. **模块与包（10'）**
   - `import / from ... import / as`
   - 标准库速览：`math`、`random`、`os`、`pathlib`、`datetime`、`json`
   - `__name__ == "__main__"` 入口判断

6. **文件读写（15'）**
   - 文本：`open(path, "r", encoding="utf-8")`、`read / readline / readlines / write`
   - 推荐写法：`with open(...) as f:` 自动关闭
   - 路径用 `pathlib.Path`（跨平台）

7. **CSV 与 JSON（10'）**
   - `csv` 模块：`csv.reader / csv.DictReader / csv.writer`
   - `json` 模块：`json.load / json.dump`，中文 `ensure_ascii=False`

8. **异常处理（10'）**
   - `try / except / else / finally`
   - 多个 except、捕获异常对象 `as e`
   - 主动抛错 `raise ValueError("msg")`
   - 自定义异常类（简述）

9. **L3 课后练习：CSV 读取清洗**
   - 读 `sales.csv`，跳过空行/异常行，按列求和，结果写回 `summary.csv`

---

## 第 4 课 · OOP 与统计分析衔接

**学习目标**：理解面向对象基础思维，能用 pip / venv 管理第三方库，并第一次跑出统计结果。

### 上半场 45 分钟 — 面向对象

1. **为什么需要类（5'）**：用函数写一组学生数据，对比类的写法

2. **类与对象（15'）**
   ```python
   class Student:
       def __init__(self, name: str, scores: list[float]):
           self.name = name
           self.scores = scores
       def average(self) -> float:
           return sum(self.scores) / len(self.scores)
       def __repr__(self) -> str:
           return f"Student(name={self.name!r}, avg={self.average():.1f})"
   ```

3. **属性与方法（10'）**
   - 实例属性 vs 类属性
   - 实例方法、类方法 `@classmethod`、静态方法 `@staticmethod`
   - 私有约定：以 `_` 或 `__` 开头（name mangling）

4. **继承与多态（10'）**
   - `class GradStudent(Student):` 覆写 `average` 加权重
   - `super().__init__(...)`
   - `isinstance / issubclass` 检查

5. **魔术方法速览（5'）**
   - `__str__ / __repr__ / __len__ / __getitem__ / __eq__`

### 下半场 45 分钟 — 走向统计分析

6. **包管理（10'）**
   - `pip install numpy pandas matplotlib`
   - 虚拟环境：VS Code 里 `Python: Create Environment` → venv
   - 锁定依赖：`pip freeze > requirements.txt`

7. **NumPy 基础（10'）**
   - `np.array([...])`、dtype、shape
   - 索引、切片、布尔掩码
   - 向量化运算、聚合：`mean / median / std / sum`

8. **pandas 基础（10'）**
   - `pd.DataFrame(data, columns=...)`
   - `df.head / info / describe`
   - 列运算、新增列、`groupby().agg()`

9. **标准库 statistics + 可视化（10'）**
   - `statistics.mean / median / stdev / variance / quantiles`
   - `matplotlib.pyplot`：`plt.hist / plt.bar / plt.plot`
   - 一个迷你案例：10 个学生成绩 → 输出均值、中位数、标准差 → 画直方图

10. **L4 课后作业：迷你描述统计**
    - 准备一份 CSV（≥ 50 行，比如 100 天打卡分钟数）
    - 用 pandas 读入，用 NumPy / statistics 算出 mean、median、std、min、max、IQR
    - 画一张直方图 + 一张按周聚合的折线图
    - 把结果写到一个 Markdown 报告里

---

## 教学配套建议

- **每个 .py 文件顶部**用三引号写清楚本节目标、运行方式、预期输出
- **课堂节奏**：讲 25 分钟 → 现场敲 10 分钟 → 答疑 5 分钟 → 留 5 分钟总结作业
- **作业交付**：放进 `python/lessons/lessonN/exercise.py`，VS Code 直接 F5 运行
- **衔接统计**：L4 下半场一定让学员**亲手跑出**一个统计图，建立"我能用它干活"的信心

## 推荐外部补充资料（课后自学）

- 官方教程：https://docs.python.org/zh-cn/3/tutorial/
- 菜鸟教程：https://www.runoob.com/python3/python3-tutorial.html
- NumPy 快速入门：https://numpy.org/doc/stable/user/quickstart.html
- pandas 10 分钟入门：https://pandas.pydata.org/docs/user_guide/10min.html
- VS Code Python 教程：https://code.visualstudio.com/docs/python/python-tutorial