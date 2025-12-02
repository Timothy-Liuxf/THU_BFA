# 线性算子的谱论

> 以下内容由 DeepSeek v3.2 Speciale 辅助整理

## 5.1 基本概念及例子

### 5.1.1 基本定义

设 $X$ 为非零复 Banach 空间，$D(A)$ 是 $X$ 的线性子空间，$A: D(A) \to X$ 是闭线性算子。对 $\lambda \in \mathbb{C}$，记 $\lambda - A = \lambda I_X - A$。

1. **特征值与点谱**  
   $\lambda$ 称为 $A$ 的**特征值**（本征值），如果存在 $x_0 \in D(A)$, $x_0 \neq 0$，使得 $A x_0 = \lambda x_0$。此时 $x_0$ 称为相应于 $\lambda$ 的特征向量。所有特征值组成的集合称为 $A$ 的**点谱**，记作 $\sigma_p(A)$。

2. **正则值与预解集**  
   若 $\lambda - A: D(A) \to X$ 是一一映射，则称 $\lambda$ 为 $A$ 的**正则值**。全体正则值之集称为 $A$ 的**预解集**，记作 $\rho(A)$。  
   **注**：若 $\lambda \in \rho(A)$，则 $(\lambda - A)^{-1}$ 是闭算子，且由闭图像定理可知 $(\lambda - A)^{-1} \in B(X)$。记 $R(\lambda, A) = (\lambda - A)^{-1}$，称为 $A$ 的**预解式**。

3. **连续谱与剩余谱**  
   设 $\lambda \notin \sigma_p(A) \cup \rho(A)$（即 $\lambda - A$ 是单射但不满）。  
   - 若 $\overline{R(\lambda - A)} = X$，则称 $\lambda$ 为 $A$ 的**连续谱点**，其全体记作 $\sigma_c(A)$。  
   - 若 $\overline{R(\lambda - A)} \subsetneq X$，则称 $\lambda$ 为 $A$ 的**剩余谱点**，其全体记作 $\sigma_r(A)$。

4. **谱**  
   定义 $A$ 的**谱**为 $\sigma(A) = \sigma_p(A) \cup \sigma_c(A) \cup \sigma_r(A)$。  
   易见 $\mathbb{C} = \rho(A) \cup \sigma(A)$（不交并），且 $\sigma_p(A),\sigma_c(A),\sigma_r(A)$ 两两不交。

### 5.1.2 例子

**例 1（乘法算子）**  
取 $X = C[0,1]$（范数 $\|x\|_\infty = \max_{t\in[0,1]}|x(t)|$），定义 $(A x)(t) = t x(t)$。则  
- $\sigma_p(A) = \varnothing$，$\sigma_c(A) = \varnothing$，$\sigma_r(A) = [0,1]$，  
- $\rho(A) = \mathbb{C} \setminus [0,1]$，$\sigma(A) = [0,1]$。

**例 2（对角算子）**  
取 $X = \ell^2$，设 $\{\alpha_n\}$ 严格单调递减趋于 $0$，定义  
$$ A(x_1,x_2,x_3,\dots) = (\alpha_1 x_1,\alpha_2 x_2,\alpha_3 x_3,\dots). $$  
则  
- $\sigma_p(A) = \{\alpha_n: n\ge 1\}$，  
- $\sigma_c(A) = \{0\}$，$\sigma_r(A) = \varnothing$，  
- $\rho(A) = \mathbb{C} \setminus (\{\alpha_n\}\cup\{0\})$。

### 5.1.3 预解式及其性质

**定义（预解式）**  
对 $\lambda \in \rho(A)$，$R(\lambda, A) = (\lambda - A)^{-1} \in B(X)$ 称为 $A$ 的预解式。

**定理 1（预解式等式）**  
对任意 $\lambda,\mu \in \rho(A)$，有  
$$ R(\lambda, A) - R(\mu, A) = (\mu - \lambda) R(\lambda, A) R(\mu, A). $$

**引理 1（von Neumann）**  
设 $A \in B(X)$ 且 $\|A\| < 1$，则 $I - A$ 在 $B(X)$ 中可逆，且  
$$ \|(I - A)^{-1}\| \le \frac{1}{1 - \|A\|}. $$

**定理 2（预解集为开集）**  
$\rho(A)$ 是 $\mathbb{C}$ 的开集。从而 $\sigma(A)$ 是 $\mathbb{C}$ 的闭集。

**证明思路**  
取 $\lambda_0 \in \rho(A)$，当 $|\lambda - \lambda_0| < \frac{1}{\|R(\lambda_0, A)\|}$ 时，利用恒等式  
$$ \lambda - A = (I + (\lambda - \lambda_0) R(\lambda_0, A)) (\lambda_0 - A) $$  
及引理 1 证明 $I + (\lambda - \lambda_0) R(\lambda_0, A)$ 可逆，从而 $\lambda \in \rho(A)$。

**定理 3（预解式的解析性）**  
映射 $\lambda \mapsto R(\lambda, A)$ 是 $\rho(A)$ 上的解析 $B(X)$-值函数，且  
$$ \frac{d}{d\lambda} R(\lambda, A) = - R(\lambda, A)^2. $$

**证明概要**  
利用预解式等式可得差商表达式  
$$ \frac{R(\lambda, A) - R(\lambda_0, A)}{\lambda - \lambda_0} = - R(\lambda, A) R(\lambda_0, A). $$  
由 $R(\lambda, A)$ 在 $\lambda_0$ 处的连续性（由定理 2 估计）知极限存在，导数为 $-R(\lambda_0, A)^2$。

### 5.1.4 向量值解析函数

为表述定理 3，需引入向量值解析概念。

**定义（向量值连续与解析）**  
设 $\Omega \subset \mathbb{C}$ 是开集，$f: \Omega \to X$。  
- $f$ 在 $t_0 \in \Omega$ 连续：$\forall \varepsilon>0,\exists\delta>0$，当 $|t-t_0|<\delta$ 时 $\|f(t)-f(t_0)\|<\varepsilon$。  
- $f$ 在 $t_0$ 可导：存在 $a \in X$，使得  
  $$ \lim_{t\to t_0} \left\|\frac{f(t)-f(t_0)}{t - t_0} - a\right\| = 0. $$  
  记 $f'(t_0)=a$。若 $f$ 在 $\Omega$ 上处处可导，则称 $f$ 在 $\Omega$ 上解析。

**注** 若 $f$ 解析，则对任意 $\phi \in X'$，$\phi \circ f$ 是通常的复解析函数。
