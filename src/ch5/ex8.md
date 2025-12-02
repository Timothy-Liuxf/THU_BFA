# 习题 5.8

设 $A \in B(X)$ 满足 $A^2=A, A \neq 0, I$. 求证: $\sigma(A)=\{0,1\}$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：由于 $A^2=A$ 且 $A\neq 0,I$，$A$ 是非平凡的幂等算子（投影）。下面分两步证明 $\sigma(A)=\{0,1\}$。

---

**第一步**：$\sigma(A)\subseteq\{0,1\}$。

设 $\lambda\notin\{0,1\}$，我们构造 $(A-\lambda I)^{-1}$。注意到 $X=\operatorname{Im}A\oplus\operatorname{Ker}A$，且在 $\operatorname{Im}A$ 上 $A=I$，在 $\operatorname{Ker}A$ 上 $A=0$。定义
$$
B=\frac{1}{1-\lambda}A-\frac{1}{\lambda}(I-A).
$$
直接计算可得对任意 $x\in X$，
$$
(A-\lambda I)B = \big(A-\lambda I\big)\left(\frac{A}{1-\lambda}-\frac{I-A}{\lambda}\right)=A+(I-A)=I.
$$
类似地 $B(A-\lambda I)=I$，故 $B=(A-\lambda I)^{-1}$。因此当 $\lambda\notin\{0,1\}$ 时，$A-\lambda I$ 可逆，从而 $\lambda\notin\sigma(A)$。于是 $\sigma(A)\subseteq\{0,1\}$。

---

**第二步**：$0,1\in\sigma(A)$。

* $0\in\sigma(A)$：若 $0\notin\sigma(A)$，则 $A$ 可逆。在等式 $A^2=A$ 两边左乘 $A^{-1}$ 得 $A=I$，与 $A\neq I$ 矛盾。故 $0\in\sigma(A)$。

* $1\in\sigma(A)$：若 $1\notin\sigma(A)$，则 $A-I$ 可逆。由 $(A-I)A=A^2-A=0$ 左乘 $(A-I)^{-1}$ 得 $A=0$，与 $A\neq 0$ 矛盾。故 $1\in\sigma(A)$。

---

综合第一步和第二步，即得 $\sigma(A)=\{0,1\}$。$\square$
