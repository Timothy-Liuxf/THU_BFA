# 习题 3.8

$H$ 为 Hilbert 空间, $M$ 为 $H$ 的闭线性子空间. 求证: $M$ 为 $H$ 上某个非零有界线性泛函的零空间当且仅当 $M^{\perp}$ 为 $H$ 的一维线性子空间.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明** 设 $H$ 是 Hilbert 空间，$M\subseteq H$ 是闭线性子空间。

**充分性**：若 $M=\ker f$，其中 $f\in H^*\setminus\{0\}$，则由 Riesz 表示定理，存在唯一的非零向量 $z\in H$ 使得 $f(x)=\langle x,z\rangle$ 对所有 $x\in H$ 成立。于是
$$
M=\{x\in H:\langle x,z\rangle =0\}=z^\perp.
$$
因为 $z\neq 0$，其正交补为 $M^\perp = (z^\perp)^\perp = \overline{\operatorname{span}\{z\}}=\operatorname{span}\{z\}$，即一维子空间。

**必要性**：若 $M^\perp$ 是一维子空间，则存在非零向量 $z\in H$ 使得 $M^\perp=\operatorname{span}\{z\}$。由于 $M$ 是闭的，由正交分解定理有 $H=M\oplus M^\perp$，且 $M=(M^\perp)^\perp$。因此
$$
M=(\operatorname{span}\{z\})^\perp = z^\perp.
$$
定义泛函 $f(x)=\langle x,z\rangle$，$f$ 是 $H$ 上的有界线性泛函，且 $f(z)=\|z\|^2\neq 0$，故 $f\neq 0$。而
$$
\ker f=\{x\in H:\langle x,z\rangle =0\}=z^\perp =M.
$$
从而 $M$ 是非零有界线性泛函 $f$ 的零空间。

综上，命题得证。
