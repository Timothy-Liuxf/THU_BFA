# 习题 4.3

设 $a_1, a_2 \in \mathbb{R}$ 固定, 考虑 $\mathbb{R}^3$ 的线性子空间
$$
Z=\left\{\left(x_1, x_2, x_3\right) \in \mathbb{R}^3: x_3=0\right\},
$$
及 $Z$ 上的线性泛函 $f\left(x_1, x_2, x_3\right)=a_1 x_1+a_2 x_2$. 求出所有 $f$ 到 $\mathbb{R}^3$ 上的线性延拓及相应线性泛函的范数, 其中 $\mathbb{R}^3$ 赋予范数 $\left\|\left(x_1, x_2, x_3\right)\right\|_2=\left(\left|x_1\right|^2+\left|x_2\right|^2+\left|x_3\right|^2\right)^{1 / 2}$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解答**  

设 $\mathbb{R}^3$ 上赋予 Euclid 范数 $\|x\|_2 = \sqrt{x_1^2+x_2^2+x_3^2}$，则它是一个 Hilbert 空间，其内积为 $\langle x,y\rangle = x_1y_1+x_2y_2+x_3y_3$。由 Riesz 表示定理，任意连续线性泛函 $F:\mathbb{R}^3\to\mathbb{R}$ 均存在唯一的 $y\in\mathbb{R}^3$ 使得 $F(x)=\langle x,y\rangle$，且 $\|F\|=\|y\|_2$。

子空间 $Z=\{(x_1,x_2,0)\mid x_1,x_2\in\mathbb{R}\}$，其上的泛函 $f(x_1,x_2,0)=a_1x_1+a_2x_2$ 已给出。设 $F$ 为 $f$ 到 $\mathbb{R}^3$ 上的任一线性延拓，则存在 $y=(y_1,y_2,y_3)\in\mathbb{R}^3$ 使得  
$$
F(x_1,x_2,x_3)=y_1x_1+y_2x_2+y_3x_3.
$$  
限制在 $Z$ 上须满足  
$$
F(x_1,x_2,0)=y_1x_1+y_2x_2 = a_1x_1+a_2x_2\quad \forall\, x_1,x_2\in\mathbb{R}.
$$  
因此 $y_1=a_1$, $y_2=a_2$，而 $y_3$ 可取任意实数。记 $y_3=c\in\mathbb{R}$，则延拓后的泛函为  
$$
\tilde{f}_c(x_1,x_2,x_3)=a_1x_1+a_2x_2+cx_3.
$$  

相应泛函的范数为  
$$
\|\tilde{f}_c\| = \|(a_1,a_2,c)\|_2 = \sqrt{a_1^2+a_2^2+c^2}.
$$  

因此，$f$ 到 $\mathbb{R}^3$ 上的所有线性延拓由参数 $c\in\mathbb{R}$ 给出，每个延拓的范数如上式。
