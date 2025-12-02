# 习题 3.7

设 $X$ 为复内积空间, $T: X \rightarrow X$ 为线性算子, 且任取 $x \in X,\langle T x, x\rangle=0$. 求证: $T=0$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**  

对任意 $x, y \in X$，由条件 $\langle T z, z \rangle = 0$ 对所有 $z \in X$ 成立。

1. **利用 $x+y$**  
   $$0 = \langle T(x+y),\, x+y \rangle = \langle Tx, x \rangle + \langle Tx, y \rangle + \langle Ty, x \rangle + \langle Ty, y \rangle = \langle Tx, y \rangle + \langle Ty, x \rangle.$$
   故得  
   $$\langle Tx, y \rangle + \langle Ty, x \rangle = 0. \tag{1}$$

2. **利用 $x+iy$**  
   $$0 = \langle T(x+iy),\, x+iy \rangle = \langle Tx, x \rangle + \langle Tx, iy \rangle + \langle T(iy), x \rangle + \langle T(iy), iy \rangle = \langle Tx, iy \rangle + \langle T(iy), x \rangle.$$
   由内积的性质（第一个变量线性，第二个变量共轭线性）有  
   $$\langle Tx, iy \rangle = \overline{i}\,\langle Tx, y \rangle = -i\langle Tx, y \rangle,$$
   且 $T(iy) = i\,Ty$，故  
   $$\langle T(iy), x \rangle = \langle i\,Ty, x \rangle = i\langle Ty, x \rangle.$$
   代入得  
   $$0 = -i\langle Tx, y \rangle + i\langle Ty, x \rangle,$$
   即  
   $$\langle Ty, x \rangle = \langle Tx, y \rangle. \tag{2}$$

将 (2) 代入 (1)：  
$$\langle Tx, y \rangle + \langle Tx, y \rangle = 0 \quad\Longrightarrow\quad 2\langle Tx, y \rangle = 0 \quad\Longrightarrow\quad \langle Tx, y \rangle = 0.$$

由于 $y \in X$ 是任意的，上式表明 $Tx$ 与所有向量正交，从而 $Tx = 0$。再由 $x$ 的任意性得 $T = 0$。∎
