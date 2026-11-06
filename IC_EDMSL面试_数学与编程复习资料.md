# 📘 IC EDMSL 面试 · 数学与编程复习资料

> **用途：** 帝国理工 EDMSL 面试的**数学 + 编程补充复习**（面试 Skill Test 部分）
> **参考来源：** 香港大学数据科学笔试大纲 + 3 份数学真题 + 计算机编程真题
> **使用方式：** 先刷主手册的 ODE/特征值/CSV 水果题，这本用来补微积分、概率、更多编程题

---

# ⚡ 快速导航

```
Part I   微积分（极限/导数/积分）         ← 补 IC 面试很少直接考但偶尔追问的基础
Part II  线性代数（矩阵/秩/特征值/方程组）← 🔥 和 IC 面试高度重叠，必刷
Part III 概率统计（概率/分布/假设检验）    ← IC 面试很少考，有空再看
Part IV  编程真题（8 道，Python 版）       ← 🔥 补充 IC CSV 水果题之外的练习
Part V   与 IC EDMSL 主手册的对照速查
```

---

# Part I · 微积分

## 1.1 极限与连续性

### 📑 知识卡片

**求极限的 4 种方法：**

| 方法 | 适用场景 | 示例 |
|------|----------|------|
| 代入法 | 直接代入 x = a 得有限值 | $\lim_{x \to 2} \frac{x+1}{x-1} = 3$ |
| 洛必达法则 | $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ | $\lim_{x \to 0} \frac{\sin x}{x} = 1$ |
| 因式分解 | $\frac{0}{0}$ 型，可约项 | $\lim_{x \to 1} \frac{x^2 - 1}{x - 1} = 2$ |
| 等价无穷小替换 | 复杂乘积型 | $x \to 0$ 时，$\sin x \sim x$，$e^x - 1 \sim x$ |

**连续性判断：** $f(x)$ 在 $x=a$ 连续 $\iff$ $\lim_{x \to a} f(x) = f(a)$

---

### 🎯 经典例题

**例题 1：** 求 $\lim_{x \to 0} \frac{e^{2x} - 1}{x}$

**解答：**

```
方法：洛必达法则（0/0 型）
分子分母分别求导：
lim (2e^{2x}) / 1 = 2e^0 = 2
```

**例题 2：** 求 $\lim_{x \to \infty} \frac{3x^2 + 2x}{x^2 - 1}$

**解答：**

```
方法：最高次项系数法（∞/∞ 型）
分子最高次项 3x²，分母 x²
极限 = 3/1 = 3
```

---

## 1.2 导数与微分

### 📑 知识卡片

**求导法则（必背）：**

| 法则 | 公式 |
|------|------|
| 幂函数 | $(x^n)' = nx^{n-1}$ |
| 乘积 | $(uv)' = u'v + uv'$ |
| 商 | $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$ |
| 链式 | $[f(g(x))]' = f'(g(x)) \cdot g'(x)$ |

**导数应用 — 极值：** $f'(x) = 0$ 处可能有极值，二阶导数判断：
- $f''(x) > 0$ → 极小值点
- $f''(x) < 0$ → 极大值点

---

### 🎯 经典例题

**例题 1：** 求 $y = x^3 \cdot e^x$ 的导数

```
乘积法则：u = x³, v = eˣ
y' = 3x²·eˣ + x³·eˣ = eˣ(3x² + x³)
```

**例题 2：** 求 $y = \ln(x^2 + 1)$ 的导数

```
链式法则：外层 f(u)=ln u, 内层 g(x)=x²+1
y' = (1/(x²+1)) · 2x = 2x/(x²+1)
```

**例题 3：** 求 $f(x) = x^4 - 2x^2 + 1$ 的极值

```
f'(x) = 4x³ - 4x = 4x(x-1)(x+1)
临界点：x = -1, 0, 1

f''(x) = 12x² - 4
f''(-1) = 8 > 0 → x=-1 极小值点，f(-1)=0
f''(0) = -4 < 0 → x=0 极大值点，f(0)=1
f''(1) = 8 > 0 → x=1 极小值点，f(1)=0
```

---

## 1.3 积分

### 📑 知识卡片

**基本积分公式：**

| 被积函数 | 积分结果 |
|----------|----------|
| $x^n$ ($n \neq -1$) | $\frac{x^{n+1}}{n+1} + C$ |
| $\frac{1}{x}$ | $\ln|x| + C$ |
| $e^x$ | $e^x + C$ |
| $\sin x$ | $-\cos x + C$ |
| $\cos x$ | $\sin x + C$ |

**积分方法：**
- **换元积分：** $\int f(g(x))g'(x)dx$，令 $u = g(x)$
- **分部积分：** $\int u dv = uv - \int v du$

---

### 🎯 经典例题

**例题 1：** $\int x \cdot e^x dx$

```
分部积分：u=x, dv=eˣdx → du=dx, v=eˣ
∫ x·eˣ dx = x·eˣ - ∫ eˣ dx = eˣ(x-1) + C
```

**例题 2：** $\int_0^2 (x^2 - 1) dx$

```
先求不定积分：[x³/3 - x]₀² = (8/3 - 2) - 0 = 2/3
```

---

# Part II · 线性代数 🔥（和 IC 面试高度重叠）

## 2.1 矩阵运算与行列式

### 📑 知识卡片

**矩阵乘法：** $C_{ij} = \sum_{k=1}^n A_{ik} B_{kj}$

**2×2 行列式：** $\det\begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$

**3×3 行列式（按第一行展开）：**

$$\det\begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix} = a(ei - fh) - b(di - fg) + c(dh - eg)$$

---

### 🎯 经典例题

**例题 1：** $\begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} \times \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$

```
C₁₁=1×5+2×7=19, C₁₂=1×6+2×8=22
C₂₁=3×5+4×7=43, C₂₂=3×6+4×8=50
→ [[19,22],[43,50]]
```

**例题 2：** $\det\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}$

```
= 1×(45-48) - 2×(36-42) + 3×(32-35)
= -3 + 12 - 9 = 0
（注意：行成比例 → 行列式为 0）
```

---

## 2.2 矩阵的秩 🔥（IC 面试追问）

### 📑 知识卡片

**秩 = 行阶梯形矩阵中非零行的数量**

**行初等变换（三种）：**
1. 交换两行
2. 某行乘非零常数
3. 某行加另一行的倍数

**重要性质：** $n \times n$ 矩阵满秩 $\iff$ $\det(A) \neq 0$ $\iff$ $A$ 可逆

---

### 🎯 经典例题

**例题：** 求 $A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 1 & 0 & 1 \end{pmatrix}$ 的秩

```
行变换：
R₂ = R₂ - 2R₁ → [[1, 2, 3], [0, 0, 0], [1, 0, 1]]
R₃ = R₃ - R₁ → [[1, 2, 3], [0, 0, 0], [0, -2, -2]]
交换 R₂、R₃ → [[1, 2, 3], [0, -2, -2], [0, 0, 0]]

非零行有 2 行 → Rank(A) = 2
```

---

## 2.3 逆矩阵

### 📑 知识卡片

**方法一（2×2 简单）：** $A^{-1} = \frac{1}{\det(A)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$

**方法二（通用）：** 高斯-约旦消元 $[A|I] \to [I|A^{-1}]$

---

### 🎯 经典例题

**例题：** 求 $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$ 的逆

```
det(A) = 4 - 1 = 3
A⁻¹ = (1/3) × [[2, -1], [-1, 2]] = [[2/3, -1/3], [-1/3, 2/3]]
```

---

## 2.4 特征值与特征向量 🔥🔥🔥（IC 面试头号考点）

> **IC 面试必考！** PCA 数学原理就基于此。

### 📑 知识卡片

**定义：** $A\mathbf{v} = \lambda\mathbf{v}$

**求解步骤：**
1. 解特征方程 $\det(A - \lambda I) = 0$ 得特征值
2. 对每个 $\lambda$，解 $(A - \lambda I)\mathbf{v} = \mathbf{0}$ 得特征向量

**重要性质：**
- 特征值之和 = **迹**（对角线元素之和）
- 特征值之积 = **行列式**
- 不同特征值对应的特征向量**线性无关**

**与 PCA 的关系（IC 面试必问）：**

> PCA 就是对**协方差矩阵**做特征值分解。特征值 $\lambda_i$ 表示对应方向上的**方差大小**，特征向量是主成分方向。按 $\lambda$ 从大到小排序，取前 k 个 → 保留最多方差。

---

### 🎯 经典例题

**例题 1：** 求 $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$ 的特征值和特征向量

```
det(A - λI) = 0:
(2-λ)² - 1 = 0 → λ² - 4λ + 3 = 0 → λ₁=1, λ₂=3

λ₁=1: (A-I)v=0 → [[1,1],[1,1]]v=0 → v₁ = (1, -1)ᵀ
λ₂=3: (A-3I)v=0 → [[-1,1],[1,-1]]v=0 → v₂ = (1, 1)ᵀ
```

**例题 2：** 求 $A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$ 的特征值

```
det(A - λI) = (3-λ)(2-λ) = 0 → λ₁=3, λ₂=2
（三角矩阵的特征值就是对角线元素）
```

---

## 2.5 线性方程组

### 📑 知识卡片

**解的情况判断（用秩）：**

| 条件 | 解的情况 |
|------|----------|
| $\text{Rank}(A) = \text{Rank}([A|\mathbf{b}]) = n$ | 唯一解 |
| $\text{Rank}(A) = \text{Rank}([A|\mathbf{b}]) < n$ | 无穷多解 |
| $\text{Rank}(A) \neq \text{Rank}([A|\mathbf{b}])$ | 无解 |

**克莱默法则（2×2/3×3 好用）：** $x_i = \frac{\det(A_i)}{\det(A)}$

---

### 🎯 经典例题

**例题：** 解 $\begin{cases} 2x + y = 5 \\ x - 2y = 0 \end{cases}$

```
克莱默法则：det(A) = 2×(-2) - 1×1 = -5
x = det([[5,1],[0,-2]]) / (-5) = (-10)/(-5) = 2
y = det([[2,5],[1,0]]) / (-5) = (-5)/(-5) = 1
→ x=2, y=1
```

---

# Part III · 概率统计（IC 面试少考，有空再看）

## 3.1 概率基础

### 📑 知识卡片

| 公式 | 内容 |
|------|------|
| 加法 | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ |
| 条件概率 | $P(B|A) = \frac{P(A \cap B)}{P(A)}$ |
| 全概率 | $P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + \cdots$ |
| 贝叶斯 | $P(B_i|A) = \frac{P(A|B_i)P(B_i)}{P(A)}$ |

---

### 🎯 经典例题

**例题：** 某工厂有 3 台机器 A/B/C，产量占比 40%/35%/25%，次品率 2%/3%/5%。随机抽一件是次品，求来自 A 的概率。

```
全概率公式：P(次品) = 0.4×0.02 + 0.35×0.03 + 0.25×0.05 = 0.031
贝叶斯：P(A|次品) = 0.4×0.02 / 0.031 ≈ 0.258
```

---

## 3.2 常见分布

### 📑 知识卡片

| 分布 | 期望 | 方差 | 适用场景 |
|------|------|------|----------|
| 二项 $B(n,p)$ | $np$ | $np(1-p)$ | n 次独立试验成功次数 |
| 泊松 $P(\lambda)$ | $\lambda$ | $\lambda$ | 单位时间稀有事件次数 |
| 正态 $N(\mu, \sigma^2)$ | $\mu$ | $\sigma^2$ | 自然界大量现象 |

---

### 🎯 经典例题

**例题 1：** 电话台每分钟呼叫 $P(3)$，求恰好 2 次的概率

```
P(X=2) = (3² · e^(-3)) / 2! ≈ 0.224
```

**例题 2：** $X \sim N(5, 4)$，求 $P(3 < X < 9)$（已知 $\Phi(2)=0.9772$, $\Phi(1)=0.8413$）

```
标准化 Z = (X-5)/2
P(3<X<9) = P(-1<Z<2) = Φ(2) - (1-Φ(1)) = 0.9772 - 0.1587 = 0.8185
```

---

## 3.3 中心极限定理 & 假设检验

### 📑 知识卡片

**中心极限定理：** 大样本下 $\bar{X}_n \sim N(\mu, \sigma^2/n)$ —— 不管总体什么分布

**假设检验：** p-value $< 0.05$ → 拒绝 $H_0$

---

### 🎯 经典例题

**例题：** 灯泡声称寿命 1000h，抽 25 只样本均值 960h，标准差 100h。$\alpha=0.05$ 下是否低于声称值？

```
H₀: μ=1000, H₁: μ<1000
Z = (960-1000)/(100/√25) = -2
p ≈ 0.0228 < 0.05 → 拒绝 H₀
→ 有足够证据认为寿命低于 1000h
```

---

# Part IV · 编程真题（Python 版，补充 IC 练习）

> IC 主手册有 CSV 水果题 + 局部最大值 + 矩阵乘法，这里补充更多题型。

## 🏆 真题 1：单词排序

**题目：** 输入 100 个单词，按字母序排序输出

```python
# 最简洁
words = [input() for _ in range(100)]
for w in sorted(words):
    print(w)

# 冒泡排序（展示原理）
def bubble_sort(words):
    n = len(words)
    for i in range(n - 1):
        for j in range(n - 1 - i):
            if words[j] > words[j + 1]:
                words[j], words[j + 1] = words[j + 1], words[j]
```

---

## 🏆 真题 2：字符串中数字求和

```python
s = input()
total = sum(int(c) for c in s if '1' <= c <= '9')
print(total)
# 输入 "abc123def4" → 1+2+3+4 = 10
```

---

## 🏆 真题 3：银行利息

**题目：** 简单利息 vs 复利

```python
principal = float(input())
rate = float(input())     # 如 0.05
years = int(input())
t = input("simple or compound: ")

if t == "simple":
    amount = principal * (1 + rate * years)
else:
    amount = principal * (1 + rate) ** years
print(f"{amount:.2f}")
```

---

## 🏆 真题 4：最大乘积（考虑负数）

**题目：** 数组中找乘积最大的两个数

```python
def max_product(nums):
    nums.sort()
    # 候选：最大两数、最小两负数、最小×最大
    return max(nums[-1]*nums[-2], nums[0]*nums[1], nums[0]*nums[-1])

# [3, -20, 5, -4, 2] → max(-20×-4=80, 5×3=15, -20×5=-100) → 80
```

---

## 🏆 真题 5：字母加密

**题目：** 小写字母 ASCII 值 + 位置 → mod 26 → 转回字母

```python
def encrypt(s):
    result = []
    for i, c in enumerate(s, start=1):
        if c == ' ':
            result.append(c)
        elif 'a' <= c <= 'z':
            pos = (ord(c) + i - ord('a')) % 26
            result.append(chr(pos + ord('a')))
        else:
            result.append(c)
    return ''.join(result)
# 'h' 第1个: (104+1-97)%26 = 8 → 'i'
```

---

## 🏆 真题 6：完美数

**题目：** 输出第 k 个完美数（真因子之和 = 自身）

```python
def is_perfect(n):
    return sum(i for i in range(1, n) if n % i == 0) == n

def kth_perfect(k):
    count, num = 0, 2
    while True:
        if is_perfect(num):
            count += 1
            if count == k: return num
        num += 1
# 1st=6, 2nd=28, 3rd=496
```

---

## 🏆 真题 7：众数

```python
from collections import Counter
nums = [1, 2, 2, 3, 3, 3]
print(Counter(nums).most_common(1)[0][0])  # 3

# 手动字典
counts = {}
for n in nums:
    counts[n] = counts.get(n, 0) + 1
print(max(counts, key=counts.get))
```

---

## 🏆 真题 8：代币兑换

**规则：** 每 10 代币换 1 green（green 每 6 换 1 yellow 余保留，yellow 每 2 换 1 white 余保留）

```python
tokens = int(input())
green = tokens // 10
yellow_from_green = green // 6
white = yellow_from_green // 2
green %= 6
yellow = yellow_from_green % 2
print(f"{green} green, {yellow} yellow, {white} white")
```

---

# Part V · 与 IC EDMSL 主手册对照速查

> 这本是**补充资料**，主手册刷完再看这本补漏。

| IC 主手册考点 | 这本对应位置 | 关系 |
|--------------|-------------|------|
| ODE 积分因子法 + Euler/RK4 | Part I 微积分 | IC 专属，这本没有 → **主手册刷** |
| 特征值/特征向量 + PCA 原理 | Part II 2.4 | 🔥 **高度重叠，共用** |
| 矩阵秩 | Part II 2.2 | 🔥 **高度重叠，共用** |
| CSV 水果题 3 种方法 | Part IV 编程题 | 🔥 主手册有，这本补充其他题 |
| list vs set / 不可变类型 | — | 主手册有，这本没重复 |
| 局部最大值 | — | 主手册有，这本没重复 |
| 微积分极限/导数/积分 | Part I | 这本更系统，**主手册没细讲** |
| 概率统计 / 假设检验 | Part III | 这本独有，IC 面试很少考 |
| 线性方程组 / 克莱默法则 | Part II 2.5 | 这本独有，IC 面试不直接考 |

---

> 💡 **复习路径建议：**
> 1. 先刷 **IC 主手册 Part III 数学 + 编程**（ODE + 特征值 + CSV 水果题）
> 2. 再看这本 **Part II 线性代数**（秩、逆、方程组）→ 补 IC 追问点
> 3. 这本 **Part IV 编程题** → 当额外练习
> 4. **Part I 微积分 + Part III 概率统计** → 有空再看，IC 面试少考
