# 习题 1.9

设 $(X, d)$ 为度量空间, $A, B$ 为 $X$ 的子集. 求证:

1. $\overline{A \cup B}=\bar{A} \cup \bar{B}$;

2. $\overline{A \cap B} \subset \bar{A} \cap \bar{B}$;

3. $(A \cap B)^{\circ}=A^{\circ} \cap B^{\circ}$;

4. $A^{\circ} \cup B^{\circ} \subset(A \cup B)^{\circ}$.

举例说明第二个和第四个包含关系可以是严格的.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解答**  

设 $(X,d)$ 为度量空间，$A,B\subset X$。

---

**1.** 证明 $\overline{A\cup B}=\bar{A}\cup\bar{B}$。

首先，由于 $A\subset A\cup B$，故 $\bar{A}\subset\overline{A\cup B}$；同理 $\bar{B}\subset\overline{A\cup B}$，从而 $\bar{A}\cup\bar{B}\subset\overline{A\cup B}$。

另一方面，$\bar{A}$ 和 $\bar{B}$ 都是闭集，有限个闭集的并仍是闭集，因此 $\bar{A}\cup\bar{B}$ 是闭集。又 $A\cup B\subset\bar{A}\cup\bar{B}$，而 $\overline{A\cup B}$ 是包含 $A\cup B$ 的最小闭集，故 $\overline{A\cup B}\subset\bar{A}\cup\bar{B}$。

综上，$\overline{A\cup B}=\bar{A}\cup\bar{B}$。

---

**2.** 证明 $\overline{A\cap B}\subset\bar{A}\cap\bar{B}$。

因为 $A\cap B\subset A$，由闭包的单调性有 $\overline{A\cap B}\subset\bar{A}$；同理 $\overline{A\cap B}\subset\bar{B}$，故 $\overline{A\cap B}\subset\bar{A}\cap\bar{B}$。

该包含关系可以是严格的。例如取 $X=\mathbb{R}$，$A=(0,1)$，$B=(1,2)$，则 $A\cap B=\varnothing$，$\overline{A\cap B}=\varnothing$，而 $\bar{A}=[0,1]$，$\bar{B}=[1,2]$，$\bar{A}\cap\bar{B}=\{1\}\neq\varnothing$，因此 $\overline{A\cap B}\subsetneq\bar{A}\cap\bar{B}$。

---

**3.** 证明 $(A\cap B)^{\circ}=A^{\circ}\cap B^{\circ}$。

若 $x\in (A\cap B)^{\circ}$，则存在 $\varepsilon>0$ 使得 $B(x,\varepsilon)\subset A\cap B$，从而 $B(x,\varepsilon)\subset A$ 且 $B(x,\varepsilon)\subset B$，因此 $x\in A^{\circ}$ 且 $x\in B^{\circ}$，即 $x\in A^{\circ}\cap B^{\circ}$。

反之，若 $x\in A^{\circ}\cap B^{\circ}$，则存在 $\varepsilon_1,\varepsilon_2>0$ 使得 $B(x,\varepsilon_1)\subset A$，$B(x,\varepsilon_2)\subset B$。取 $\varepsilon=\min\{\varepsilon_1,\varepsilon_2\}$，则 $B(x,\varepsilon)\subset A$ 且 $B(x,\varepsilon)\subset B$，故 $B(x,\varepsilon)\subset A\cap B$，即 $x\in(A\cap B)^{\circ}$。

因此等式成立。

---

**4.** 证明 $A^{\circ}\cup B^{\circ}\subset(A\cup B)^{\circ}$。

若 $x\in A^{\circ}\cup B^{\circ}$，则 $x\in A^{\circ}$ 或 $x\in B^{\circ}$。当 $x\in A^{\circ}$ 时，存在 $\varepsilon>0$ 使 $B(x,\varepsilon)\subset A\subset A\cup B$，故 $x\in(A\cup B)^{\circ}$；当 $x\in B^{\circ}$ 时同理。因此 $A^{\circ}\cup B^{\circ}\subset(A\cup B)^{\circ}$。

该包含关系可以是严格的。例如取 $X=\mathbb{R}$，$A=[0,1]$，$B=[1,2]$，则 $A^{\circ}=(0,1)$，$B^{\circ}=(1,2)$，$A^{\circ}\cup B^{\circ}=(0,1)\cup(1,2)$。而 $A\cup B=[0,2]$，$(A\cup B)^{\circ}=(0,2)$，显然 $1\in(A\cup B)^{\circ}$ 但 $1\notin A^{\circ}\cup B^{\circ}$，因此 $A^{\circ}\cup B^{\circ}\subsetneq(A\cup B)^{\circ}$。

证毕。
