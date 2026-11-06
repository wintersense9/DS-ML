# 🚀 IC 帝国理工 EDMSL 面试冲刺手册

---

# ⚡ 时间紧？按这个优先级

| 天数 | 干什么 | 预计耗时 |
|------|--------|---------|
| Day 1 | 🔥 ODE 积分因子法 + Euler 法能手算 + 特征值/特征向量 | 4-5h |
| Day 2 | 🔥 Python 水果 CSV 题 3 种写法 + list/set/不可变类型 + 局部最大值 | 4-5h |
| Day 3 | General 话术 + 项目 L1-L5 过一遍 + 模拟一遍 | 3-4h |

> 如果只够 1 天：**先刷 Part III 数学和编程**，General 临场编也能圆，数学编程不会直接挂。

---

# 🗺️ 面试全景卡（先心里有数）

| 项目 | 详情 |
|------|------|
| 形式 | Zoom / Skype 平行线上 |
| 时长 | 20-40 min（大部分 30 min） |
| 考官 | EDMSL 项目在职教授 |
| 结构 | General (5-10min) → Project (10-15min) → **Skill Test (10-15min)** ← 最容易挂 |

---

# Part I · General Questions

> 目标：流利 1 分钟，引导面试官到你准备好的方向。不要等面试官问，主动说。

---

## 1.1 必考 5 题 + 你可以直接套的模板

### Q1 · Motivation（第一个问题，必问）

**面试官在想啥：** 你真的了解 EDMSL 还是海投？

**回答框架（三段式，别废话）：**

```
① 触发点：一个具体的经历/课程（别说"我一直想学AI"）
② 匹配点：IC EDMSL 的 1-2 门具体课程 + 你的背景能贡献啥
③ 差异化：IC EDMSL 和别的学校不一样的地方
```

**示例（直接抄结构，替换成你自己的）：**

> "My interest started when I took *Computational Methods in Geography* — we used PCA to analyze 50 years of temperature anomaly data across China, and that's when I realized environmental problems need both domain knowledge and ML. IC EDMSL's *Advanced Machine Learning for Earth Observation* directly covers this intersection. Also, your group's work on climate model downscaling is exactly what I want to explore."

**❌ 千万别这么答：** "I've always been interested in AI and environment, so IC is my dream school."

---

### Q2 · 1 分钟自我介绍

**结构：** `姓名 + 学校/专业 + 1 个硬亮点（GPA/排名/奖项）+ 1 个相关经历收尾`

**最后一句必须引向你准备好的项目** —— 这样面试官自然就顺着你准备好的方向问了。

---

### Q3 · CV / PS 细节追问

面试官能把你 CV 上**每一行**挖 3 层。你必须能对 CV 上每个项目说出：

| 他们会挖什么 | 你要能答 |
|-------------|----------|
| 做了什么 | 一句话概述 |
| 为什么选这个方法 | 方法选择的理由（试过什么，比下来哪个好） |
| 底层数学/技术 | 能用的 → 能讲清底层（用了 PCA → 能说特征值分解） |
| 结果靠谱吗 | 不能只说"效果好" → 说验证方法 |

**你可以这样练：** 把 CV 逐行念出来，自己随机挑一行，追问自己 3 层，答不上来就标记回去补。

---

### Q4 · Why IC / Why EDMSL

**别和 Motivation 重复。** 重点讲 IC 的**资源 / 声誉 / 地理位置**。

### Q5 · 未来规划

**别空。** 结合 EDMSL 的方向。别说 "I want to be a data scientist" —— 要说 "I want to work on remote sensing + ML for carbon monitoring"。

---

## 1.2 General 部分速查表

| # | 题目 | 优先级 | 你要做什么 |
|---|------|--------|-----------|
| 1 | Walk me through your CV | ★★★★★ | 准备 2 分钟版本，主动引导 |
| 2 | Why EDMSL at IC？ | ★★★★★ | 上官网找 1-2 门具体课程塞进回答 |
| 3 | 最相关的一门课 | ★★★★ | 找 EDMSL 课程手册里的对应项 |
| 4 | 会什么编程语言？哪个最熟？ | ★★★★ | 诚实说，但准备一个能展开的 |
| 5 | numpy / pandas 会吗 | ★★★ | 会就说，准备一个场景 |
| 6 | Python class / OOP 经验？ | ★★★ | 准备一个小例子 |
| 7 | Future career plan | ★★ | 别空，结合 EDMSL 方向 |

---

# Part II · Personal Project

> **第二大挂科重灾区！** 你以为讲清楚做了什么就够了？面试官追到数学原理。

---

## 2.1 项目答辩清单（对着自己的项目逐个 ✅）

| 层级 | 他们会问 | 你要能答 |
|------|---------|----------|
| **L1 · 做了什么** | "Tell me about this project" | 一句话概述 + 你的具体贡献 |
| **L2 · 用了什么** | "What method did you use" | 具体算法/工具/数据量 |
| **L3 · 为什么选这个** | "Why not try X instead" | 试过啥方法比较下来选这个的理由 |
| **L4 · 数学原理** | "Can you explain how that works mathematically" | 底层公式能讲（PCA → 特征值分解，RF → Gini/信息增益） |
| **L5 · 结果靠谱吗** | "How did you verify your results" | 交叉验证 / 时间分割 / 混淆矩阵 —— 不能只说 score |

**自测方法：** 拿你的主项目，从 L1 一路自问自答到 L5。任何一层卡壳 → 回去补。

---

## 2.2 高分项目三个标志（看你中了几个）

1. **有数据量：** 至少几千条（不是 100 条 demo）
2. **有比较：** 试过多种方法并说清楚为什么选 A 不选 B
3. **有验证：** 有交叉验证 / 时间分割，不是只给一个 accuracy

---

# 🔥 Part III-A · Math 数学（头号挂科元凶）

> 面经里超过一半的人说数学部分答得不好。这部分 **必须练到手算不卡**。
> 每个考点：**知识卡片记住 → 真题手算一遍 → 练习题自测**

---

## 3.1 微分方程 ODE（必考 ★★★★★）

### 📑 你必须记住的公式

**一阶线性 ODE 标准形式：**

$$\frac{dy}{dx} + P(x)y = Q(x)$$

**积分因子法四步（背下来）：**

```
Step 1: 算积分因子  μ(x) = e^(∫ P(x) dx)
Step 2: 两边乘 μ(x) → 左边凑成 d/dx [μ(x)·y]
Step 3: 两边积分 → μ(x)·y = ∫ μ(x)Q(x)dx + C
Step 4: 解出 y → y = (1/μ(x)) [∫ μ(x)Q(x)dx + C]
```

**Euler 法（显式欧拉，数值解必考）：**

$$y_{n+1} = y_n + h \cdot f(x_n, y_n)$$

就是：**下一个点 = 当前点 + 步长 × 当前斜率**

**RK4（精度更高，偶尔考）：**

$$k_1 = f(x_n, y_n)$$
$$k_2 = f(x_n + h/2, y_n + h k_1/2)$$
$$k_3 = f(x_n + h/2, y_n + h k_2/2)$$
$$k_4 = f(x_n + h, y_n + h k_3)$$
$$y_{n+1} = y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)$$

---

### 🎯 真题手算（现在就拿纸算一遍）

**真题 1：** 求解 $y' - 2y = e^{3x}$，$y(0) = 0$

<details><summary>点我看标准答案</summary>

```
Step 1: P(x) = -2, Q(x) = e^{3x}
Step 2: μ(x) = e^{∫(-2)dx} = e^{-2x}
Step 3: e^{-2x}·y' - 2e^{-2x}·y = e^{x}
        → d/dx [e^{-2x}·y] = e^{x}
Step 4: e^{-2x}·y = ∫ e^{x}dx = e^{x} + C
Step 5: y = e^{3x} + C·e^{2x}
Step 6: y(0)=0 → 0 = 1 + C → C = -1
        → y = e^{3x} - e^{2x}
```

</details>

---

**真题 2（Parastoo 老师考过）：** Euler 法 h=0.1，解 $y' = y + x$，$y(0)=1$，走到 x=0.3

<details><summary>点我看标准答案</summary>

```
f(x,y) = y + x, h = 0.1

x0=0,  y0=1
x1=0.1, y1 = 1 + 0.1*(1+0) = 1.1
x2=0.2, y2 = 1.1 + 0.1*(1.1+0.1) = 1.22
x3=0.3, y3 = 1.22 + 0.1*(1.22+0.2) = 1.3622

→ y(0.3) ≈ 1.3622
```

</details>

---

### 📝 自测题（遮住答案算）

| # | 题目 | 难度 |
|---|------|------|
| 1 | 求解 $y' + 3y = 6$ | 基础 |
| 2 | 求解 $y' - y = \cos x$，$y(0) = 1$ | 中等 |
| 3 | Euler h=0.2 解 $y' = 2y - x$，$y(0)=1$，到 x=0.4 | 基础 |
| 4 | RK4 h=0.1 解 $y' = x - y$，$y(0)=2$，到 x=0.2 | 中等 |

---

## 3.2 线性代数（必考 ★★★★★）

### 📑 你必须记住的

**特征值 & 特征向量：**

$$A\mathbf{v} = \lambda\mathbf{v} \quad \Rightarrow \quad \det(A - \lambda I) = 0$$

**PCA 和特征值（面经高频追问，必须能说）：**

> PCA 就是对**协方差矩阵**做特征值分解。
> 
> - 特征值 $\lambda_i$ = 对应方向上的**方差大小**
> - 特征向量 = 主成分的**方向**
> - 按 $\lambda_1 \geq \lambda_2 \geq \cdots$ 排序，取前 k 个 → 保留最多的方差

**矩阵的秩：**

- 线性无关行/列的最大数量
- 满秩 $\iff$ $\det(A) \neq 0$ $\iff$ 可逆

---

### 🎯 真题手算

**真题 1：** 求 $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$ 的特征值和特征向量

<details><summary>点我看标准答案</summary>

```
det(A - λI) = 0:
|2-λ   1  |
| 1   2-λ | = 0

(2-λ)² - 1 = 0 → λ² - 4λ + 3 = 0
→ λ₁ = 1, λ₂ = 3

λ₁=1: (A-I)v=0 → v₁ = (1, -1)ᵀ
λ₂=3: (A-3I)v=0 → v₂ = (1, 1)ᵀ
```

</details>

---

**真题 2：** 矩阵 $A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \end{pmatrix}$ 的秩？为什么？

<details><summary>点我看标准答案</summary>

```
Rank = 1

因为第二行 = 第一行 × 2，两行线性相关。
所以只有 1 行线性无关 → 秩 = 1。
```

</details>

---

### 📝 自测题

| # | 题目 | 难度 |
|---|------|------|
| 1 | $A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$ 的特征值 | 基础 |
| 2 | $A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}$ 的秩 | 中等 |
| 3 | 为什么 PCA 要找最大的特征值？（用嘴说出来） | 中等 |

---

## 3.3 微积分 & 统计

### 📑 你要能说清楚的

**梯度下降（面经考过）：**

$$\theta_{t+1} = \theta_t - \eta \cdot \nabla_\theta J(\theta)$$

> 梯度指向**损失上升最快**的方向 → 负梯度就是**下降最快**的方向。

**局部最大值：** 比左右邻居都大的位置（结合编程考）

**95% 置信区间：** $\bar{x} \pm 1.96 \cdot \frac{\sigma}{\sqrt{n}}$

---

# 🔥 Part III-B · Code 编程（重灾区）

> ⚠️ **水果 CSV 题出现 4+ 次！** 必须熟。
> 编程考察方式：**至少两种方法** + **解释每一行怎么想的** + 可能追问数学原理

---

## 3.4 Python 基础概念（必考 ★★★★★）

### 📑 一眼看懂的对比表

| 属性 | list | set | tuple |
|------|------|-----|-------|
| 有序 | ✅ | ❌ | ✅ |
| 可变 | ✅ | ✅ | ❌ |
| 允许重复 | ✅ | ❌ | ✅ |
| 常用 | 索引、append | 去重、集合运算 | 不可变 key |

**不可变类型（immutable）：** `int, float, str, tuple, frozenset, bool`
> tuple 可以做 dict key，list 不行。因为 dict key 必须 hashable（= 不可变）。

---

### 🎯 经典真题

**Q1：list 和 set 有什么区别？**

<details><summary>标准答案</summary>

1. list 有序、可 index；set 无序、不能 index
2. list 允许重复；set 自动去重
3. set 查找 O(1)（哈希），list 查找 O(n)
4. set 支持 union / intersection / difference
5. set 元素必须是 hashable（不可变类型）

</details>

---

**Q2：Python 哪些类型是 immutable？**

<details><summary>标准答案</summary>

`int, float, str, tuple, frozenset, bytes, bool`

面试加分补充：这就是为什么 tuple 能做 dict key 但 list 不行 —— hashable 要求不可变。

</details>

---

## 3.5 编程实操题（按面经频率排序）

### 🏆 题目 1：CSV 水果平均重量（4+ 次！必须熟）

**面试官说：** "给你一个 CSV，每行水果名和重量，算每种水果的平均重量。至少两种方法。"

#### 方法一：pandas（最简洁）

```python
import pandas as pd

df = pd.read_csv("fruits.csv")
result = df.groupby("fruit")["weight"].mean()
print(result)
```

#### 方法二：csv + defaultdict（面试官最爱看，不用 pandas）

```python
import csv
from collections import defaultdict

fruit_weight_sum = defaultdict(float)   # 自动处理新 key
fruit_count = defaultdict(int)

with open("fruits.csv", "r") as f:
    reader = csv.DictReader(f)          # 自动读表头
    for row in reader:
        fruit_weight_sum[row["fruit"]] += float(row["weight"])
        fruit_count[row["fruit"]] += 1

for fruit in fruit_weight_sum:
    print(f"{fruit}: {fruit_weight_sum[fruit]/fruit_count[fruit]:.2f}")
```

#### 方法三：numpy（面试官追问第三种）

```python
import pandas as pd
import numpy as np

df = pd.read_csv("fruits.csv")
print(df.groupby("fruit")["weight"].apply(np.mean))
```

> **练习建议：** 建一个 `fruits.csv` 假数据，三种方法都跑一遍，面试时确保不卡。

---

### 🏆 题目 2：找数组局部最大值

**面试官说：** "写函数找出数组中所有局部最大值"

```python
def find_local_max(arr):
    result = []
    for i in range(1, len(arr) - 1):    # 跳过首尾
        if arr[i] > arr[i-1] and arr[i] > arr[i+1]:
            result.append((i, arr[i]))
    return result

# 测试
data = [1, 3, 2, 5, 1, 4, 3]
print(find_local_max(data))   # [(1, 3), (3, 5), (5, 4)]
```

---

### 🏆 题目 3：矩阵乘法（不用 numpy）

```python
def matrix_multiply(A, B):
    m, n = len(A), len(A[0])
    n2, p = len(B), len(B[0])
    result = [[0]*p for _ in range(m)]
    for i in range(m):
        for j in range(p):
            for k in range(n):
                result[i][j] += A[i][k] * B[k][j]
    return result
```

---

### 📝 编程自测（现在打开 Jupyter 写）

| # | 题目 | 必过？ |
|---|------|--------|
| 1 | CSV 水果平均重量（至少两种方法） | 🔥 必过 |
| 2 | 数组局部最大值 | 🔥 必过 |
| 3 | 矩阵乘法（不用 numpy） | 建议过 |
| 4 | defaultdict 统计词频 | 建议过 |
| 5 | 手写一个 class（deposit/withdraw） | 了解 |

---

# Part IV · 面试官画像（先查你被分配给谁）

| 老师 | 风格 | 你要重点准备 |
|------|------|-------------|
| **Parastoo Salehi** | 简洁直接，不绕弯 | 线性 ODE + Python 局部最大值 |
| **Marijan** | 喜欢追问，数值方法专业 | ODE 数值解（Euler/RK4）能手算 + CV 深挖到 L4 |
| **Fredrick** | 节奏快，追问应用 | 准备 1-2 个 ODE 的物理/环境应用场景 |
| **Nelson** | 标准考察 | 基础题别错，走标准流程就行 |
| **Ames** | 经典题套路 | 水果题 3 种方法 + 特征值稳 |

---

# Part V · 考前 Checklist

## ✅ 进场前 5 分钟，对照自查

### General
- [ ] Motivation 三段式能流利讲 1 分钟
- [ ] CV 每一行能答到 L3 以上
- [ ] 准备好 3whys

### Project
- [ ] 主项目 L1-L5 全部能答
- [ ] 能说清楚方法比较结论
- [ ] 能说清楚验证方法

### Math 🔥
- [ ] 一阶线性 ODE 积分因子法能手算
- [ ] Euler 法能手算
- [ ] 特征值/特征向量能手算 2×2
- [ ] PCA ↔ 特征值分解的逻辑通

### Code 🔥
- [ ] 水果 CSV 至少两种方法熟写
- [ ] list vs set vs tuple 区别能说
- [ ] 不可变类型能说全
- [ ] 局部最大值会写

### 心态
- [ ] 准备好诚实回答："Hmm, I'm not entirely sure, but let me think about it..."
- [ ] 知道老师很 nice，答错会引导，别慌

---

## ⏰ 面试 30 分钟时间分配（心里有数）

```
0:00 - 0:30   开场 + Intro（主动引到你准备的方向）
0:30 - 3:00   Motivation + 3whys
3:00 - 10:00  Personal Project（用 L1-L5 主动展开）
10:00 - 25:00 Math + Code（核心！慢慢来，说 how you think）
25:00 - 30:00 Q&A（反问要准备 1-2 个有水平的）
```

---

## 💡 反问环节（你问什么？）

**好问题（显得你调研过）：**
> "I read that your group is working on X — can you tell me more about how EDMSL students get involved?"
> "The course *Advanced ML for Earth Observation* looks very relevant — is it offered in Term 1?"

**❌ 别问：** "When will I get my offer？" / "Is this interview important？"

---

# 📎 最后想说

面经里最常见的反馈是：

> "数学部分答得不好，但老师很 nice 会引导"
> "编程 CSV 那道我卡了，但说 how you think 也能过"
> "紧张很正常，诚实比乱答好"
