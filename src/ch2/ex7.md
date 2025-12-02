# 习题 2.7

设 $X$ 为赋范空间, 求证:

(1) 任给 $A, B \subset X, \bar{A}+\bar{B} \subset \overline{A+B}$;

(2)若 $x_0 \in X$ 为定点, 则 $A \subset X$ 为开集当且仅当 $x_0+A$ 为开集;

(3)若 $x_0 \in X$ 为定点, 则 $A \subset X$ 为闭集当且仅当 $x_0+A$ 为闭集;

(4) 若 $A \subset X, B \subset X$ 中至少有一个为开集, 则 $A+B$ 也为开集;

(5) 若 $A^{\circ} \neq \emptyset$, 则 0 为 $A-A=\{x-y: x, y \in A\}$ 的内点.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

(1) 证明：设 $x \in \overline{A} + \overline{B}$，则存在 $a \in \overline{A}$，$b \in \overline{B}$ 使得 $x = a+b$。由闭包定义，存在序列 $\{a_n\}\subset A$，$\{b_n\}\subset B$ 满足 $a_n\to a$，$b_n\to b$。令 $x_n = a_n+b_n \in A+B$，则  
$$
\|x_n - x\| \le \|a_n - a\| + \|b_n - b\|\to 0,
$$  
故 $x_n \to x$，因此 $x \in \overline{A+B}$。所以 $\overline{A}+\overline{B} \subset \overline{A+B}$。

(2) 证明：定义平移映射 $T_{x_0}(x) = x_0 + x$，它是等距同胚（因为 $\|T_{x_0}(x)-T_{x_0}(y)\| = \|x-y\|$，且逆为 $T_{-x_0}$）。由于同胚保持开集性质，$A$ 开当且仅当 $x_0+A = T_{x_0}(A)$ 开。也可直接论证：若 $A$ 开，对任意 $y = x_0+a \in x_0+A$，存在 $\varepsilon>0$ 使得 $B(a,\varepsilon)\subset A$，则 $B(y,\varepsilon) = x_0 + B(a,\varepsilon) \subset x_0+A$，故 $x_0+A$ 开；反之，若 $x_0+A$ 开，则 $A = -x_0 + (x_0+A)$ 同样为开集。因此结论成立。

(3) 证明：平移同胚也保持闭集。若 $A$ 闭，任取序列 $\{y_n\}\subset x_0+A$ 且 $y_n\to y$，则存在 $a_n\in A$ 使得 $y_n = x_0 + a_n$。于是 $a_n = y_n - x_0 \to y - x_0$。由 $A$ 闭知 $y - x_0 \in A$，故 $y = x_0 + (y - x_0) \in x_0+A$，因此 $x_0+A$ 闭。反之，若 $x_0+A$ 闭，则 $A = -x_0 + (x_0+A)$ 同样闭。得证。

(4) 证明：不妨设 $A$ 是开集（$B$ 开时类似）。任取 $z = a + b \in A+B$，其中 $a\in A$，$b\in B$。由 $A$ 开，存在 $\varepsilon>0$ 使得 $B(a,\varepsilon) \subset A$。现对任意 $w \in B(z,\varepsilon)$，有 $\|w - z\| < \varepsilon$。令 $a' = a + (w - z)$，则 $\|a' - a\| = \|w - z\| < \varepsilon$，故 $a' \in B(a,\varepsilon) \subset A$。于是 $w = a' + b \in A + B$。因此 $B(z,\varepsilon) \subset A+B$，即 $z$ 为内点。由于 $z$ 任意，$A+B$ 是开集。

(5) 证明：因为 $A^\circ \neq \emptyset$，存在 $a_0 \in A^\circ$ 及 $\delta>0$ 使得 $B(a_0,\delta) \subset A$。则对任意 $z \in B(0,\delta)$，有 $\|z\| < \delta$。注意到 $a_0+z \in B(a_0,\delta) \subset A$，且 $a_0 \in A$，故 $z = (a_0+z) - a_0 \in A - A$。因此 $B(0,\delta) \subset A - A$，即 $0$ 是 $A-A$ 的内点。
