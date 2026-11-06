# 📘 IC EDMSL 面试 · 数学与编程复习资料
# 📘 IC EDMSL Interview · Math & Programming Review Materials

> **用途：** 帝国理工 EDMSL 面试的**数学 + 编程补充复习**（面试 Skill Test 部分）
> **EN:** **Purpose:** Supplementary review for Imperial College EDMSL interview **Math + Programming** (Skill Test section)
>
> **参考来源：** 香港大学数据科学笔试大纲 + 3 份数学真题 + 计算机编程真题
> **EN:** **Sources:** HKU Data Science written exam syllabus + 3 past math papers + computer programming past papers
>
> **使用方式：** 先刷主手册的 ODE/特征值/CSV 水果题，这本用来补微积分、概率、更多编程题
> **EN:** **How to use:** First complete the main handbook's ODE/eigenvalues/CSV fruit problems; use this book to supplement calculus, probability, and more programming problems

---

# ⚡ 快速导航
# ⚡ Quick Navigation

```
Part I   微积分（极限/导数/积分）         ← 补 IC 面试很少直接考但偶尔追问的基础
Part II  线性代数（矩阵/秩/特征值/方程组）← 🔥 和 IC 面试高度重叠，必刷
Part III 概率统计（概率/分布/假设检验）    ← IC 面试很少考，有空再看
Part IV  编程真题（8 道，Python 版）       ← 🔥 补充 IC CSV 水果题之外的练习
Part V   与 IC EDMSL 主手册的对照速查
```

**EN:**
```
Part I   Calculus (limits/derivatives/integrals)        ← Supplementary fundamentals, rarely tested directly but occasionally asked in follow-ups
Part II  Linear Algebra (matrices/rank/eigenvalues/systems) ← 🔥 Highly overlaps with IC interview, must study
Part III Probability & Statistics (probability/distributions/hypothesis testing) ← Rarely tested in IC interview, read if time permits
Part IV  Past Programming Questions (8 questions, Python) ← 🔥 Supplementary practice beyond IC CSV fruit problems
Part V   Quick Reference Comparison with IC EDMSL Main Handbook
```

---

# Part I · 微积分
# Part I · Calculus

## 1.1 极限与连续性
## 1.1 Limits and Continuity

### 📑 知识卡片
### 📑 Knowledge Card

**求极限的 4 种方法：**
**EN: Four Methods for Computing Limits:**

| 方法 | 适用场景 | 示例 |
|------|----------|------|
| 代入法 | 直接代入 x = a 得有限值 | $\lim_{x \to 2} \frac{x+1}{x-1} = 3$ |
| 洛必达法则 | $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$ | $\lim_{x \to 0} \frac{\sin x}{x} = 1$ |
| 因式分解 | $\frac{0}{0}$ 型，可约项 | $\lim_{x \to 1} \frac{x^2 - 1}{x - 1} = 2$ |
| 等价无穷小替换 | 复杂乘积型 | $x \to 0$ 时，$\sin x \sim x$，$e^x - 1 \sim x$ |

**EN:**
| Method | Use Case | Example |
|--------|----------|---------|
| Substitution | Direct substitution gives finite value | $\lim_{x \to 2} \frac{x+1}{x-1} = 3$ |
| L'Hôpital's Rule | $\frac{0}{0}$ or $\frac{\infty}{\infty}$ | $\lim_{x \to 0} \frac{\sin x}{x} = 1$ |
| Factoring | $\frac{0}{0}$ form with cancellable terms | $\lim_{x \to 1} \frac{x^2 - 1}{x - 1} = 2$ |
| Equivalent Infinitesimal Substitution | Complex product forms | As $x \to 0$, $\sin x \sim x$, $e^x - 1 \sim x$ |

**连续性判断：** $f(x)$ 在 $x=a$ 连续 $\iff$ $\lim_{x \to a} f(x) = f(a)$
**EN: Continuity Check:** $f(x)$ is continuous at $x=a$ $\iff$ $\lim_{x \to a} f(x) = f(a)$

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题 1：** 求 $\lim_{x \to 0} \frac{e^{2x} - 1}{x}$
**EN: Example 1:** Find $\lim_{x \to 0} \frac{e^{2x} - 1}{x}$

**解答：**
**EN: Solution:**

```
方法：洛必达法则（0/0 型）
分子分母分别求导：
lim (2e^{2x}) / 1 = 2e^0 = 2
```

**例题 2：** 求 $\lim_{x \to \infty} \frac{3x^2 + 2x}{x^2 - 1}$
**EN: Example 2:** Find $\lim_{x \to \infty} \frac{3x^2 + 2x}{x^2 - 1}$

**解答：**
**EN: Solution:**

```
方法：最高次项系数法（∞/∞ 型）
分子最高次项 3x²，分母 x²
极限 = 3/1 = 3
```

---

## 1.2 导数与微分
## 1.2 Derivatives and Differentiation

### 📑 知识卡片
### 📑 Knowledge Card

**求导法则（必背）：**
**EN: Differentiation Rules (Must Memorize):**

| 法则 | 公式 |
|------|------|
| 幂函数 | $(x^n)' = nx^{n-1}$ |
| 乘积 | $(uv)' = u'v + uv'$ |
| 商 | $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$ |
| 链式 | $[f(g(x))]' = f'(g(x)) \cdot g'(x)$ |

**EN:**
| Rule | Formula |
|------|---------|
| Power Rule | $(x^n)' = nx^{n-1}$ |
| Product Rule | $(uv)' = u'v + uv'$ |
| Quotient Rule | $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$ |
| Chain Rule | $[f(g(x))]' = f'(g(x)) \cdot g'(x)$ |

**导数应用 — 极值：** $f'(x) = 0$ 处可能有极值，二阶导数判断：
**EN: Application of Derivatives — Extrema:** Extrema may occur where $f'(x) = 0$, use second derivative test:
- $f''(x) > 0$ → 极小值点 / **Local minimum**
- $f''(x) < 0$ → 极大值点 / **Local maximum**

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题 1：** 求 $y = x^3 \cdot e^x$ 的导数
**EN: Example 1:** Find the derivative of $y = x^3 \cdot e^x$

乘积法则：$u = x^3$, $v = e^x$

$y' = 3x^2 \cdot e^x + x^3 \cdot e^x = e^x(3x^2 + x^3)$

**例题 2：** 求 $y = \ln(x^2 + 1)$ 的导数
**EN: Example 2:** Find the derivative of $y = \ln(x^2 + 1)$

链式法则：外层 $f(u) = \ln u$, 内层 $g(x) = x^2 + 1$

$y' = \frac{1}{x^2+1} \cdot 2x = \frac{2x}{x^2+1}$

**例题 3：** 求 $f(x) = x^4 - 2x^2 + 1$ 的极值
**EN: Example 3:** Find the extrema of $f(x) = x^4 - 2x^2 + 1$

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
## 1.3 Integration

### 📑 知识卡片
### 📑 Knowledge Card

**基本积分公式：**
**EN: Basic Integration Formulas:**

| 被积函数 | 积分结果 |
|----------|----------|
| $x^n$ ($n \neq -1$) | $\frac{x^{n+1}}{n+1} + C$ |
| $\frac{1}{x}$ | $\ln|x| + C$ |
| $e^x$ | $e^x + C$ |
| $\sin x$ | $-\cos x + C$ |
| $\cos x$ | $\sin x + C$ |

**EN:**
| Integrand | Integral Result |
|-----------|-----------------|
| $x^n$ ($n \neq -1$) | $\frac{x^{n+1}}{n+1} + C$ |
| $\frac{1}{x}$ | $\ln|x| + C$ |
| $e^x$ | $e^x + C$ |
| $\sin x$ | $-\cos x + C$ |
| $\cos x$ | $\sin x + C$ |

**积分方法：**
**EN: Integration Methods:**
- **换元积分 / Substitution:** $\int f(g(x))g'(x)dx$，令 $u = g(x)$ / let $u = g(x)$
- **分部积分 / Integration by Parts:** $\int u dv = uv - \int v du$

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题 1：** $\int x \cdot e^x dx$
**EN: Example 1:** $\int x \cdot e^x dx$

分部积分：$u = x$, $dv = e^x\, dx$ → $du = dx$, $v = e^x$

$\int x \cdot e^x\, dx = x \cdot e^x - \int e^x\, dx = e^x(x-1) + C$

**例题 2：** $\int_0^2 (x^2 - 1) dx$
**EN: Example 2:** $\int_0^2 (x^2 - 1) dx$

```
先求不定积分：[x³/3 - x]₀² = (8/3 - 2) - 0 = 2/3
```

---

# Part II · 线性代数 🔥（和 IC 面试高度重叠）
# Part II · Linear Algebra 🔥 (Highly overlaps with IC interview)

## 2.1 矩阵运算与行列式
## 2.1 Matrix Operations and Determinants

### 📑 知识卡片
### 📑 Knowledge Card

**矩阵乘法：** $C_{ij} = \sum_{k=1}^n A_{ik} B_{kj}$
**EN: Matrix Multiplication:** $C_{ij} = \sum_{k=1}^n A_{ik} B_{kj}$

**2×2 行列式：** $$\det\begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$$
**EN: 2×2 Determinant:** $$\det\begin{pmatrix} a & b \\ c & d \end{pmatrix} = ad - bc$$

**3×3 行列式（按第一行展开）：**
**EN: 3×3 Determinant (expanding along the first row):**

$$$\det\begin{pmatrix} a & b & c \\ d & e & f \\ g & h & i \end{pmatrix} = a(ei - fh) - b(di - fg) + c(dh - eg)$$$

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题 1：** $$\begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} \times \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$$
**EN: Example 1:** $$\begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix} \times \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$$

```
C₁₁=1×5+2×7=19, C₁₂=1×6+2×8=22
C₂₁=3×5+4×7=43, C₂₂=3×6+4×8=50
→ [[19,22],[43,50]]
```

**例题 2：** $$\det\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}$$
**EN: Example 2:** $$\det\begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{pmatrix}$$

```
= 1×(45-48) - 2×(36-42) + 3×(32-35)
= -3 + 12 - 9 = 0
（注意：行成比例 → 行列式为 0）
(Note: rows are proportional → determinant is 0)
```

---

## 2.2 矩阵的秩 🔥（IC 面试追问）
## 2.2 Rank of a Matrix 🔥 (IC interview follow-up)

### 📑 知识卡片
### 📑 Knowledge Card

**秩 = 行阶梯形矩阵中非零行的数量**
**EN: Rank = number of non-zero rows in row echelon form**

**行初等变换（三种）：**
**EN: Three Elementary Row Operations:**
1. 交换两行 / Swap two rows
2. 某行乘非零常数 / Multiply a row by a non-zero constant
3. 某行加另一行的倍数 / Add a multiple of one row to another row

**重要性质：** $n \times n$ 矩阵满秩 $\iff$ $\det(A) \neq 0$ $\iff$ $A$ 可逆
**EN: Important Property:** An $n \times n$ matrix has full rank $\iff$ $\det(A) \neq 0$ $\iff$ $A$ is invertible

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题：** 求 $$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 1 & 0 & 1 \end{pmatrix}$$ 的秩
**EN: Example:** Find the rank of $$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 1 & 0 & 1 \end{pmatrix}$$

```
行变换：
R₂ = R₂ - 2R₁ → [[1, 2, 3], [0, 0, 0], [1, 0, 1]]
R₃ = R₃ - R₁ → [[1, 2, 3], [0, 0, 0], [0, -2, -2]]
交换 R₂、R₃ → [[1, 2, 3], [0, -2, -2], [0, 0, 0]]

非零行有 2 行 → Rank(A) = 2
```

---

## 2.3 逆矩阵
## 2.3 Inverse Matrix

### 📑 知识卡片
### 📑 Knowledge Card

**方法一（2×2 简单）：** $$A^{-1} = \frac{1}{\det(A)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$
**EN: Method 1 (simple for 2×2):** $$A^{-1} = \frac{1}{\det(A)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$

**方法二（通用）：** 高斯-约旦消元 $[A|I] \to [I|A^{-1}]$
**EN: Method 2 (general):** Gauss-Jordan elimination $[A|I] \to [I|A^{-1}]$

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题：** 求 $$A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$ 的逆
**EN: Example:** Find the inverse of $$A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$

```
det(A) = 4 - 1 = 3
A⁻¹ = (1/3) × [[2, -1], [-1, 2]] = [[2/3, -1/3], [-1/3, 2/3]]
```

---

## 2.4 特征值与特征向量 🔥🔥🔥（IC 面试头号考点）
## 2.4 Eigenvalues and Eigenvectors 🔥🔥🔥 (#1 topic in IC interview)

> **IC 面试必考！** PCA 数学原理就基于此。
> **EN:** **Guaranteed in IC interview!** This is the mathematical foundation of PCA.

### 📑 知识卡片
### 📑 Knowledge Card

**定义：** $A\mathbf{v} = \lambda\mathbf{v}$
**EN: Definition:** $A\mathbf{v} = \lambda\mathbf{v}$

**求解步骤：**
**EN: Solution Steps:**
1. 解特征方程 $\det(A - \lambda I) = 0$ 得特征值 / Solve characteristic equation $\det(A - \lambda I) = 0$ to get eigenvalues
2. 对每个 $\lambda$，解 $(A - \lambda I)\mathbf{v} = \mathbf{0}$ 得特征向量 / For each $\lambda$, solve $(A - \lambda I)\mathbf{v} = \mathbf{0}$ to get eigenvectors

**重要性质：**
**EN: Important Properties:**
- 特征值之和 = **迹**（对角线元素之和）/ Sum of eigenvalues = **trace** (sum of diagonal elements)
- 特征值之积 = **行列式** / Product of eigenvalues = **determinant**
- 不同特征值对应的特征向量**线性无关** / Eigenvectors corresponding to different eigenvalues are **linearly independent**

**与 PCA 的关系（IC 面试必问）：**
**EN: Relationship with PCA (must-know for IC interview):**

> PCA 就是对**协方差矩阵**做特征值分解。特征值 $\lambda_i$ 表示对应方向上的**方差大小**，特征向量是主成分方向。按 $\lambda$ 从大到小排序，取前 k 个 → 保留最多方差。
> **EN:** PCA is essentially eigenvalue decomposition on the **covariance matrix**. Eigenvalues $\lambda_i$ represent the **variance** in each direction, and eigenvectors are the principal component directions. Sort by $\lambda$ from largest to smallest, take the top k → preserves the most variance.

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题 1：** 求 $$A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$ 的特征值和特征向量
**EN: Example 1:** Find eigenvalues and eigenvectors of $$A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$

$\det(A - \lambda I) = 0$:

$(2-\lambda)^2 - 1 = 0$ → $\lambda^2 - 4\lambda + 3 = 0$ → $\lambda_1 = 1$, $\lambda_2 = 3$

$\lambda_1 = 1$: $(A-I)\mathbf{v} = 0$ → $$\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}\mathbf{v} = 0$$ → $\mathbf{v}_1 = (1, -1)^T$

$\lambda_2 = 3$: $(A-3I)\mathbf{v} = 0$ → $$\begin{pmatrix} -1 & 1 \\ 1 & -1 \end{pmatrix}\mathbf{v} = 0$$ → $\mathbf{v}_2 = (1, 1)^T$

**例题 2：** 求 $$A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$$ 的特征值
**EN: Example 2:** Find eigenvalues of $$A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$$

$\det(A - \lambda I) = (3-\lambda)(2-\lambda) = 0$ → $\lambda_1 = 3$, $\lambda_2 = 2$
（三角矩阵的特征值就是对角线元素 / Eigenvalues of a triangular matrix are just the diagonal elements）

---

## 2.5 线性方程组
## 2.5 Systems of Linear Equations

### 📑 知识卡片
### 📑 Knowledge Card

**解的情况判断（用秩）：**
**EN: Determining Solution Type (using rank):**

| 条件 | 解的情况 |
|------|----------|
| $\text{Rank}(A) = \text{Rank}([A|\mathbf{b}]) = n$ | 唯一解 |
| $\text{Rank}(A) = \text{Rank}([A|\mathbf{b}]) < n$ | 无穷多解 |
| $\text{Rank}(A) \neq \text{Rank}([A|\mathbf{b}])$ | 无解 |

**EN:**
| Condition | Solution Type |
|-----------|---------------|
| $\text{Rank}(A) = \text{Rank}([A|\mathbf{b}]) = n$ | Unique solution |
| $\text{Rank}(A) = \text{Rank}([A|\mathbf{b}]) < n$ | Infinitely many solutions |
| $\text{Rank}(A) \neq \text{Rank}([A|\mathbf{b}])$ | No solution |

**克莱默法则（2×2/3×3 好用）：** $x_i = \frac{\det(A_i)}{\det(A)}$
**EN: Cramer's Rule (works well for 2×2/3×3):** $x_i = \frac{\det(A_i)}{\det(A)}$

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题：** 解 $$\begin{cases} 2x + y = 5 \\ x - 2y = 0 \end{cases}$$
**EN: Example:** Solve $$\begin{cases} 2x + y = 5 \\ x - 2y = 0 \end{cases}$$

```
克莱默法则：det(A) = 2×(-2) - 1×1 = -5
x = det([[5,1],[0,-2]]) / (-5) = (-10)/(-5) = 2
y = det([[2,5],[1,0]]) / (-5) = (-5)/(-5) = 1
→ x=2, y=1
```

---

# Part III · 概率统计（IC 面试少考，有空再看）
# Part III · Probability & Statistics (Rarely tested in IC interview, read if time permits)

## 3.1 概率基础
## 3.1 Fundamentals of Probability

### 📑 知识卡片
### 📑 Knowledge Card

| 公式 | 内容 |
|------|------|
| 加法 | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ |
| 条件概率 | $P(B|A) = \frac{P(A \cap B)}{P(A)}$ |
| 全概率 | $P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + \cdots$ |
| 贝叶斯 | $P(B_i|A) = \frac{P(A|B_i)P(B_i)}{P(A)}$ |

**EN:**
| Formula | Content |
|---------|---------|
| Addition Rule | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ |
| Conditional Probability | $P(B|A) = \frac{P(A \cap B)}{P(A)}$ |
| Law of Total Probability | $P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + \cdots$ |
| Bayes' Theorem | $P(B_i|A) = \frac{P(A|B_i)P(B_i)}{P(A)}$ |

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题：** 某工厂有 3 台机器 A/B/C，产量占比 40%/35%/25%，次品率 2%/3%/5%。随机抽一件是次品，求来自 A 的概率。
**EN: Example:** A factory has 3 machines A/B/C with production proportions 40%/35%/25% and defect rates 2%/3%/5%. A randomly selected item is defective — find the probability it came from A.

全概率公式：$P(\text{次品}) = 0.4 \times 0.02 + 0.35 \times 0.03 + 0.25 \times 0.05 = 0.031$

贝叶斯：$P(A|\text{次品}) = \frac{0.4 \times 0.02}{0.031} \approx 0.258$

---

## 3.2 常见分布
## 3.2 Common Distributions

### 📑 知识卡片
### 📑 Knowledge Card

| 分布 | 期望 | 方差 | 适用场景 |
|------|------|------|----------|
| 二项 $B(n,p)$ | $np$ | $np(1-p)$ | n 次独立试验成功次数 |
| 泊松 $P(\lambda)$ | $\lambda$ | $\lambda$ | 单位时间稀有事件次数 |
| 正态 $N(\mu, \sigma^2)$ | $\mu$ | $\sigma^2$ | 自然界大量现象 |

**EN:**
| Distribution | Expectation | Variance | Use Case |
|--------------|-------------|----------|----------|
| Binomial $B(n,p)$ | $np$ | $np(1-p)$ | Number of successes in n independent trials |
| Poisson $P(\lambda)$ | $\lambda$ | $\lambda$ | Number of rare events per unit time |
| Normal $N(\mu, \sigma^2)$ | $\mu$ | $\sigma^2$ | Many natural phenomena |

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题 1：** 电话台每分钟呼叫 $P(3)$，求恰好 2 次的概率
**EN: Example 1:** A call center receives calls at $P(3)$ per minute. Find the probability of exactly 2 calls.

$P(X=2) = \frac{3^2 \cdot e^{-3}}{2!} \approx 0.224$

**例题 2：** $X \sim N(5, 4)$，求 $P(3 < X < 9)$（已知 $\Phi(2)=0.9772$, $\Phi(1)=0.8413$）
**EN: Example 2:** $X \sim N(5, 4)$, find $P(3 < X < 9)$ (given $\Phi(2)=0.9772$, $\Phi(1)=0.8413$)

标准化 $Z = \frac{X-5}{2}$

$P(3 < X < 9) = P(-1 < Z < 2) = \Phi(2) - (1-\Phi(1)) = 0.9772 - 0.1587 = 0.8185$

---

## 3.3 中心极限定理 & 假设检验
## 3.3 Central Limit Theorem & Hypothesis Testing

### 📑 知识卡片
### 📑 Knowledge Card

**中心极限定理：** 大样本下 $\bar{X}_n \sim N(\mu, \sigma^2/n)$ —— 不管总体什么分布
**EN: Central Limit Theorem:** For large samples, $\bar{X}_n \sim N(\mu, \sigma^2/n)$ — regardless of the underlying population distribution.

**假设检验：** p-value $< 0.05$ → 拒绝 $H_0$
**EN: Hypothesis Testing:** p-value $< 0.05$ → reject $H_0$

---

### 🎯 经典例题
### 🎯 Classic Examples

**例题：** 灯泡声称寿命 1000h，抽 25 只样本均值 960h，标准差 100h。$\alpha=0.05$ 下是否低于声称值？
**EN: Example:** Light bulbs claim 1000h lifespan. A sample of 25 has mean 960h and std 100h. At $\alpha=0.05$, is the lifespan below the claimed value?

$H_0: \mu = 1000$, $H_1: \mu < 1000$

$Z = \frac{960-1000}{100/\sqrt{25}} = -2$

$p \approx 0.0228 < 0.05$ → 拒绝 $H_0$ / reject $H_0$

→ 有足够证据认为寿命低于 1000h / Sufficient evidence that lifespan is below 1000h

---

# Part IV · 编程真题（Python 版，补充 IC 练习）
# Part IV · Past Programming Questions (Python, supplementary practice for IC)

> IC 主手册有 CSV 水果题 + 局部最大值 + 矩阵乘法，这里补充更多题型。
> **EN:** The IC main handbook covers CSV fruit problems + local maxima + matrix multiplication. Here we add more question types.

## 🏆 真题 1：单词排序
## 🏆 Past Question 1: Word Sorting

**题目：** 输入 100 个单词，按字母序排序输出
**EN: Problem:** Input 100 words, sort alphabetically and output

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
## 🏆 Past Question 2: Sum of Digits in String

```python
s = input()
total = sum(int(c) for c in s if '1' <= c <= '9')
print(total)
# 输入 "abc123def4" → 1+2+3+4 = 10
# Input "abc123def4" → 1+2+3+4 = 10
```

---

## 🏆 真题 3：银行利息
## 🏆 Past Question 3: Bank Interest

**题目：** 简单利息 vs 复利
**EN: Problem:** Simple interest vs compound interest

```python
principal = float(input())
rate = float(input())     # 如 0.05 / e.g. 0.05
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
## 🏆 Past Question 4: Maximum Product (considering negatives)

**题目：** 数组中找乘积最大的两个数
**EN: Problem:** Find two numbers in the array with the maximum product

```python
def max_product(nums):
    nums.sort()
    # 候选：最大两数、最小两负数、最小×最大
    # Candidates: largest two, smallest two negatives, smallest × largest
    return max(nums[-1]*nums[-2], nums[0]*nums[1], nums[0]*nums[-1])

# [3, -20, 5, -4, 2] → max(-20×-4=80, 5×3=15, -20×5=-100) → 80
```

---

## 🏆 真题 5：字母加密
## 🏆 Past Question 5: Letter Encryption

**题目：** 小写字母 ASCII 值 + 位置 → mod 26 → 转回字母
**EN: Problem:** Take lowercase letter ASCII value + position → mod 26 → convert back to letter

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
## 🏆 Past Question 6: Perfect Numbers

**题目：** 输出第 k 个完美数（真因子之和 = 自身）
**EN: Problem:** Output the k-th perfect number (sum of proper divisors = number itself)

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
## 🏆 Past Question 7: Mode

```python
from collections import Counter
nums = [1, 2, 2, 3, 3, 3]
print(Counter(nums).most_common(1)[0][0])  # 3

# 手动字典 / Manual dictionary
counts = {}
for n in nums:
    counts[n] = counts.get(n, 0) + 1
print(max(counts, key=counts.get))
```

---

## 🏆 真题 8：代币兑换
## 🏆 Past Question 8: Token Exchange

**规则：** 每 10 代币换 1 green（green 每 6 换 1 yellow 余保留，yellow 每 2 换 1 white 余保留）
**EN: Rules:** Every 10 tokens → 1 green (every 6 greens → 1 yellow with remainder kept, every 2 yellows → 1 white with remainder kept)

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
# Part V · Quick Reference Comparison with IC EDMSL Main Handbook

> 这本是**补充资料**，主手册刷完再看这本补漏。
> **EN:** This is **supplementary material**. Complete the main handbook first, then use this to fill gaps.

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

**EN:**
| IC Main Handbook Topic | This Book Location | Relationship |
|------------------------|-------------------|--------------|
| ODE integrating factor + Euler/RK4 | Part I Calculus | IC-exclusive, not in this book → **study main handbook** |
| Eigenvalues/eigenvectors + PCA principles | Part II 2.4 | 🔥 **Highly overlapping, shared** |
| Matrix rank | Part II 2.2 | 🔥 **Highly overlapping, shared** |
| CSV fruit problems (3 methods) | Part IV Programming | 🔥 In main handbook, this book adds other problems |
| list vs set / immutable types | — | In main handbook, not repeated here |
| Local maxima | — | In main handbook, not repeated here |
| Calculus limits/derivatives/integrals | Part I | This book is more systematic, **not covered in detail in main handbook** |
| Probability & statistics / hypothesis testing | Part III | Unique to this book, rarely tested in IC interview |
| Linear systems / Cramer's rule | Part II 2.5 | Unique to this book, not directly tested in IC interview |

---

> 💡 **复习路径建议：**
> 1. 先刷 **IC 主手册 Part III 数学 + 编程**（ODE + 特征值 + CSV 水果题）
> 2. 再看这本 **Part II 线性代数**（秩、逆、方程组）→ 补 IC 追问点
> 3. 这本 **Part IV 编程题** → 当额外练习
> 4. **Part I 微积分 + Part III 概率统计** → 有空再看，IC 面试少考

**EN:**
> 💡 **Recommended Study Path:**
> 1. First complete **IC Main Handbook Part III Math + Programming** (ODE + eigenvalues + CSV fruit problems)
> 2. Then study this book's **Part II Linear Algebra** (rank, inverse, systems) → covers IC follow-up questions
> 3. This book's **Part IV Programming** → use as extra practice
> 4. **Part I Calculus + Part III Probability & Statistics** → read if time permits, rarely tested in IC interview
