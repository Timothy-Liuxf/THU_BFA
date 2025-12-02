# 习题 1.2

设 $(X, d)$ 为度量空间 $, x, y, z, w \in X$. 求证
$$
|d(x, y)-d(z, w)| \leq d(x, z)+d(y, w).
$$

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：由度量 $d$ 的三角不等式，对任意 $x,y,z,w \in X$，有
$$
d(x,y) \le d(x,z) + d(z,y) \le d(x,z) + d(z,w) + d(w,y) = d(x,z) + d(z,w) + d(y,w),
$$
移项即得
$$
d(x,y) - d(z,w) \le d(x,z) + d(y,w). \tag{1}
$$
同理，
$$
d(z,w) \le d(z,x) + d(x,w) \le d(z,x) + d(x,y) + d(y,w) = d(x,z) + d(x,y) + d(y,w),
$$
移项得
$$
d(z,w) - d(x,y) \le d(x,z) + d(y,w). \tag{2}
$$
综合 $(1)$ 和 $(2)$，便有
$$
|d(x,y)-d(z,w)| \le d(x,z) + d(y,w).
$$
