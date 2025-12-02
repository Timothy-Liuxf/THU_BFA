# 习题 2.1

判定下述 $\mathbb{R}^3$ 的哪些子集构成 $\mathbb{R}^3$ 的线性子空间(这里 $\boldsymbol{x}=\left(x_1, x_2, x_3\right) \in \mathbb{R}^3$ ).

1. 所有满足 $x_1=x_2$, 且 $x_3=0$ 的 $\boldsymbol{x}$;

2. 所有满足 $x_2=x_1+1$ 的 $\boldsymbol{x}$;

3. 所有满足 $x_1 \geq 0$ 且 $x_2 \leq 0$ 的 $\boldsymbol{x}$;

4. 所有满足 $x_1+x_2-x_3=0$ 的 $\boldsymbol{x}$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解**  $\mathbb{R}^3$ 的子集 $M$ 是线性子空间当且仅当 $M\neq\varnothing$，且对加法和数乘封闭，即  
- $0\in M$；  
- 对任意 $x,y\in M$，有 $x+y\in M$；  
- 对任意 $\alpha\in\mathbb{R}$ 和 $x\in M$，有 $\alpha x\in M$。

以下逐一判定。

---

**1. $M_1=\{\boldsymbol{x}=(x_1,x_2,x_3)\in\mathbb{R}^3\mid x_1=x_2,\;x_3=0\}$**  

- **零向量**：$(0,0,0)$ 满足 $0=0$ 且 $0=0$，故 $0\in M_1$。  
- **加法封闭**：任取 $\boldsymbol{u}=(u_1,u_1,0),\ \boldsymbol{v}=(v_1,v_1,0)\in M_1$，则  
  \[
  \boldsymbol{u}+\boldsymbol{v}=(u_1+v_1,\ u_1+v_1,\ 0),
  \]  
  满足 $x_1=x_2$ 且 $x_3=0$，故 $\boldsymbol{u}+\boldsymbol{v}\in M_1$。  
- **数乘封闭**：任取 $\alpha\in\mathbb{R}$，$\boldsymbol{u}=(u_1,u_1,0)\in M_1$，则  
  \[
  \alpha\boldsymbol{u}=(\alpha u_1,\ \alpha u_1,\ 0),
  \]  
  满足 $x_1=x_2$ 且 $x_3=0$，故 $\alpha\boldsymbol{u}\in M_1$。  

因此 $M_1$ 是 $\mathbb{R}^3$ 的线性子空间。

---

**2. $M_2=\{\boldsymbol{x}=(x_1,x_2,x_3)\in\mathbb{R}^3\mid x_2=x_1+1\}$**  

- **零向量**：$(0,0,0)$ 应满足 $0=0+1$，即 $0=1$，不成立，故 $0\notin M_2$。  

不满足子空间的基本要求，因此 $M_2$ 不是线性子空间。

（亦可验证加法或数乘不封闭，但无需再证。）

---

**3. $M_3=\{\boldsymbol{x}=(x_1,x_2,x_3)\in\mathbb{R}^3\mid x_1\ge0,\;x_2\le0\}$**  

- **零向量**：$(0,0,0)$ 满足 $0\ge0$ 且 $0\le0$，故 $0\in M_3$。  
- **加法封闭**：任取 $\boldsymbol{u}=(u_1,u_2,u_3),\ \boldsymbol{v}=(v_1,v_2,v_3)\in M_3$，则 $u_1,v_1\ge0$，$u_2,v_2\le0$。  
  于是 $u_1+v_1\ge0$，$u_2+v_2\le0$，故 $\boldsymbol{u}+\boldsymbol{v}\in M_3$。  
- **数乘封闭**：取 $\boldsymbol{u}=(1,-1,0)\in M_3$，令 $\alpha=-1\in\mathbb{R}$，则  
  \[
  \alpha\boldsymbol{u}=(-1,1,0),
  \]  
  此时 $x_1=-1<0$，不满足 $x_1\ge0$，故 $\alpha\boldsymbol{u}\notin M_3$。  

数乘不封闭，因此 $M_3$ 不是线性子空间。

---

**4. $M_4=\{\boldsymbol{x}=(x_1,x_2,x_3)\in\mathbb{R}^3\mid x_1+x_2-x_3=0\}$**  

- **零向量**：$(0,0,0)$ 满足 $0+0-0=0$，故 $0\in M_4$。  
- **加法封闭**：任取 $\boldsymbol{u}=(u_1,u_2,u_3),\ \boldsymbol{v}=(v_1,v_2,v_3)\in M_4$，即 $u_1+u_2-u_3=0$，$v_1+v_2-v_3=0$。  
  则  
  \[
  (\boldsymbol{u}+\boldsymbol{v})_1+(\boldsymbol{u}+\boldsymbol{v})_2-(\boldsymbol{u}+\boldsymbol{v})_3=(u_1+v_1)+(u_2+v_2)-(u_3+v_3)=(u_1+u_2-u_3)+(v_1+v_2-v_3)=0,
  \]  
  故 $\boldsymbol{u}+\boldsymbol{v}\in M_4$。  
- **数乘封闭**：任取 $\alpha\in\mathbb{R}$，$\boldsymbol{u}\in M_4$，则  
  \[
  (\alpha u_1)+(\alpha u_2)-(\alpha u_3)=\alpha(u_1+u_2-u_3)=\alpha\cdot0=0,
  \]  
  故 $\alpha\boldsymbol{u}\in M_4$。  

因此 $M_4$ 是 $\mathbb{R}^3$ 的线性子空间。

---

**结论**：构成 $\mathbb{R}^3$ 线性子空间的集合是 **1** 和 **4**。
