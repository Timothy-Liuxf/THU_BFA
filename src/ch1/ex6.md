# 习题 1.6

设 $(X, d)$ 为度量空间, 求证: $M \subset X$ 为开集当且仅当 $M$ 可以表示成 $X$ 中某些开球的并集.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：  

设 \((X,d)\) 为度量空间，\(M \subset X\)。  

**充分性**（\(\Leftarrow\)）：若 \(M\) 可表示成若干开球的并集，即存在指标集 \(I\) 使得  
$$
M = \bigcup_{i\in I} B(x_i, r_i),
$$  
其中每个 \(B(x_i, r_i) = \{ y\in X \mid d(x_i,y) < r_i \}\) 为开球。  
在度量空间中，每个开球都是开集（证明见注）。而开集的任意并仍为开集，因此 \(M\) 是开集。  

**必要性**（\(\Rightarrow\)）：若 \(M\) 是开集，则对任意 \(x\in M\)，存在 \(\varepsilon_x > 0\) 使得  
$$
B(x, \varepsilon_x) \subseteq M.
$$  
考虑集族 \(\{ B(x, \varepsilon_x) \mid x\in M \}\)，显然  
$$
\bigcup_{x\in M} B(x, \varepsilon_x) \subseteq M,
$$  
且对每个 \(x\in M\) 有 \(x \in B(x, \varepsilon_x)\)，故  
$$
M \subseteq \bigcup_{x\in M} B(x, \varepsilon_x).
$$  
从而 \(M = \bigcup_{x\in M} B(x, \varepsilon_x)\)，即 \(M\) 可表示为 \(X\) 中某些开球的并集。  

**注**：开球是开集的证明——任取 \(y \in B(x,r)\)，令 \(\delta = r - d(x,y) > 0\)，则对任意 \(z \in B(y,\delta)\)，有  
$$
d(x,z) \le d(x,y) + d(y,z) < d(x,y) + \delta = r,
$$  
故 \(z \in B(x,r)\)，即 \(B(y,\delta) \subseteq B(x,r)\)。因此 \(B(x,r)\) 为开集。  

综上，命题得证。
