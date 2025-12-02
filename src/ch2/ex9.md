# 习题 2.9

设 $X$ 为赋范空间 $, x_n, y_n, x, y \in X, \alpha_n, \alpha \in \mathbb{K}$. 若 $x_n \rightarrow x, y_n \rightarrow y, \alpha_n \rightarrow \alpha$, 求证 : $x_n+y_n$ $\rightarrow x+y, \alpha_n x_n \rightarrow \alpha x$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**  

**加法收敛性**：  
因 $x_n\to x$，对任意 $\varepsilon>0$，存在 $N_1\in\mathbb{N}$ 使当 $n\geq N_1$ 时 $\|x_n-x\|<\varepsilon/2$。  
因 $y_n\to y$，存在 $N_2\in\mathbb{N}$ 使当 $n\geq N_2$ 时 $\|y_n-y\|<\varepsilon/2$。  
取 $N=\max\{N_1,N_2\}$，则当 $n\geq N$ 时有  

$$
\|(x_n+y_n)-(x+y)\|=\|(x_n-x)+(y_n-y)\|\leq\|x_n-x\|+\|y_n-y\|<\frac{\varepsilon}{2}+\frac{\varepsilon}{2}=\varepsilon,
$$

故 $x_n+y_n\to x+y$。

**数乘收敛性**：  
由 $\alpha_n\to\alpha$ 知 $\{\alpha_n\}$ 有界，即存在 $M>0$ 使 $|\alpha_n|\leq M$ 对所有 $n$ 成立。  

对任意 $\varepsilon>0$：  

- 因 $x_n\to x$，存在 $N_1$ 使当 $n\geq N_1$ 时 $\|x_n-x\|<\dfrac{\varepsilon}{2(M+1)}$；  
- 因 $\alpha_n\to\alpha$，存在 $N_2$ 使当 $n\geq N_2$ 时 $|\alpha_n-\alpha|<\dfrac{\varepsilon}{2(\|x\|+1)}$。  

取 $N=\max\{N_1,N_2\}$，则当 $n\geq N$ 时，有  

$$
\begin{aligned}
\|\alpha_n x_n-\alpha x\|
&=\|\alpha_n(x_n-x)+(\alpha_n-\alpha)x\| \\
&\leq |\alpha_n|\|x_n-x\|+|\alpha_n-\alpha|\|x\| \\
&< M\cdot\frac{\varepsilon}{2(M+1)}+\frac{\varepsilon}{2(\|x\|+1)}\cdot\|x\| \\
&<\frac{\varepsilon}{2}+\frac{\varepsilon}{2}=\varepsilon.
\end{aligned}
$$

（当 $x=0$ 时第二项为 $0$，不等式依然成立。）  

因此 $\alpha_n x_n\to\alpha x$。  

证毕。
