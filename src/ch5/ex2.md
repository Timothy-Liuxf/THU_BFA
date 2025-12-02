# 习题 5.2

设 $a<b$. 求一个有界线性算子 $A \in B(C[0,1])$, 使得 $\sigma(A)=[a, b]$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

设 $C[0,1]$ 为定义在 $[0,1]$ 上的复值连续函数空间，赋予上确界范数 $\|f\|_\infty = \sup_{t\in[0,1]}|f(t)|$。  
定义算子 $A: C[0,1] \to C[0,1]$ 如下：  
$$
(Af)(t) = \varphi(t) f(t), \quad t\in[0,1],
$$  
其中 $\varphi(t) = a + (b-a)t$。  

**1. 线性性：** 对任意 $f,g\in C[0,1]$ 和 $\alpha,\beta\in\mathbb{C}$，  
$$
A(\alpha f+\beta g)(t) = \varphi(t)(\alpha f(t)+\beta g(t)) = \alpha \varphi(t)f(t)+\beta\varphi(t)g(t) = \alpha(Af)(t)+\beta(Ag)(t),
$$  
故 $A$ 线性。

**2. 有界性：** 对任意 $f\in C[0,1]$，  
$$
\|Af\|_\infty = \sup_{t\in[0,1]}|\varphi(t)f(t)| \le \sup_{t\in[0,1]}|\varphi(t)|\cdot\|f\|_\infty = \max\{|a|,|b|\}\|f\|_\infty,
$$  
因此 $A$ 有界，且 $\|A\| = \sup_{t\in[0,1]}|\varphi(t)| = \max\{|a|,|b|\}$。

**3. 谱的计算：** 记 $\sigma(A)$ 为 $A$ 的谱。  
对任意 $\lambda\in\mathbb{C}$，算子 $A-\lambda I$ 为乘法算子：  
$$
((A-\lambda I)f)(t) = (\varphi(t)-\lambda) f(t).
$$  
- **若 $\lambda\notin [a,b]$：**  
  则对任意 $t\in[0,1]$，$\varphi(t)-\lambda \neq 0$（当 $\lambda$ 为实数且不在 $[a,b]$ 时，$\varphi(t)-\lambda$ 恒不为零；当 $\lambda$ 有非零虚部时，其模恒为正）。  
  此时 $1/(\varphi-\lambda)$ 是 $[0,1]$ 上的连续函数，因而有界。定义乘法算子 $B$ 为  
  $$
  (Bg)(t) = \frac{1}{\varphi(t)-\lambda}\, g(t).
  $$  
  容易验证 $B$ 是 $(A-\lambda I)$ 的有界逆算子，故 $\lambda\in\rho(A)$（预解集）。

- **若 $\lambda\in [a,b]$：**  
  由 $\varphi$ 的连续性及 $\varphi([0,1])=[a,b]$，存在 $t_0\in[0,1]$ 使得 $\varphi(t_0)=\lambda$。  
  对任意 $f\in C[0,1]$，有 $((A-\lambda I)f)(t_0)=(\varphi(t_0)-\lambda)f(t_0)=0$，因此 $(A-\lambda I)$ 的值域包含于子空间  
  $$
  \{g\in C[0,1] : g(t_0)=0\}.
  $$  
  由于存在函数 $h\in C[0,1]$ 满足 $h(t_0)\neq 0$（例如 $h\equiv 1$），$h$ 不在该值域中，故 $A-\lambda I$ 不是满射，从而不可逆（不存在有界逆）。因此 $\lambda\in\sigma(A)$。

综上所述，$\sigma(A) = [a,b]$。
