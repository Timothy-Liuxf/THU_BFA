# 习题 5.1

设 $v \in C[0,1]$ 固定, 考虑 $C[0,1]$ 上的算子 $(A x)(t)=v(t) x(t)$, 求 $\sigma(A)$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

我们考虑复值连续函数空间 $C[0,1]$，赋予上确界范数 $\|x\|_\infty = \sup_{t\in[0,1]}|x(t)|$。算子 $A$ 定义为 $(Ax)(t)=v(t)x(t)$，其中 $v\in C[0,1]$ 是固定的函数。下面求 $A$ 的谱 $\sigma(A)$。

**定理**：$\sigma(A)=v([0,1])=\{\,v(t)\mid t\in[0,1]\,\}$。

**证明**：记 $R=v([0,1])$。因为 $v$ 连续且 $[0,1]$ 紧，所以 $R$ 是 $\mathbb{C}$ 中的紧集（从而是闭集）。

1. **若 $\lambda\notin R$，则 $\lambda\in\rho(A)$（预解集）**。  
   由于 $\lambda\notin R$，对任意 $t\in[0,1]$ 有 $\lambda\neq v(t)$。定义函数 $g(t)=(\lambda-v(t))^{-1}$。由于 $|\lambda-v(t)|$ 是连续正函数，在紧集 $[0,1]$ 上有正的最小值，故 $g$ 连续且有界。定义乘法算子 $B$ 为 $(By)(t)=g(t)y(t)$。容易验证 $B$ 是有界线性算子，并且  
   $$
   B(\lambda I-A)=(\lambda I-A)B=I,
   $$  
   即 $B=(\lambda I-A)^{-1}$。因此 $\lambda\in\rho(A)$。

2. **若 $\lambda\in R$，则 $\lambda\in\sigma(A)$**。  
   存在 $t_0\in[0,1]$ 使得 $v(t_0)=\lambda$。考虑常值函数 $y(t)\equiv1\in C[0,1]$。假设存在 $x\in C[0,1]$ 满足 $(\lambda I-A)x=y$，即  
   $$
   (\lambda-v(t))x(t)=1\quad\text{对一切 }t\in[0,1].
   $$  
   则在 $t_0$ 处有 $(\lambda-v(t_0))x(t_0)=0\cdot x(t_0)=1$，矛盾。因此方程无解，说明 $y$ 不在 $(\lambda I-A)$ 的值域中，从而 $\lambda I-A$ 不是满射，故 $\lambda\in\sigma(A)$。  
   （注：即使 $v$ 为常数 $\lambda_0$，此时 $A=\lambda_0 I$，上述论证同样成立：当 $\lambda=\lambda_0$ 时，$\lambda I-A=0$，显然不可逆。）

综合 1 和 2 即得 $\sigma(A)=R$。$\square$

**结论**：乘法算子 $A$ 的谱恰为连续函数 $v$ 的值域。
