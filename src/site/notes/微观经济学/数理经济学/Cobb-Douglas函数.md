---
{"dg-publish":true,"permalink":"/微观经济学/数理经济学/Cobb-Douglas函数/","tags":["数理经济学"],"created":"2025-09-12 18:58","updated":"2025-11-08 12:30"}
---


Cobb-Douglas function

$$
Y=x_{1}^{\alpha}x_{2}^\beta
$$

核心特征：

$$
\frac{\text{Expenditure on }x_{1}}{\text{Expenditure on }x_{2}}=\frac{\alpha}{\beta}
$$

## 效用最大化

$$
\begin{align*}
\max&\ u=x_1^\alpha x_2^\beta \\
\text{s.t.}&\ p_1x_1+p_2x_2=m
\end{align*}
$$

The Lagrangian for this problem is

$$
L=x_1^\alpha x_2^\beta+\lambda(m-p_1x_1-p_2x_2)
$$

F.O.C.

$$
\begin{align*}
\frac{\partial L}{\partial x_1}&=\alpha x_1^{\alpha-1}x_2^\beta-\lambda p_1=0 \\
\frac{\partial L}{\partial x_2}&=\beta x_1^\alpha x_2^{\beta-1}-\lambda p_2=0
\end{align*}
$$

which implies

$$
\frac{p_1x_1}{p_2x_2}=\frac{\alpha}{\beta}
$$

代入预算约束解得 Marshallian demand function

$$
\begin{align*}
x_1^*&=\frac{\frac{\alpha}{\alpha+\beta} m}{p_1} \\
x_2^*&=\frac{\frac{\beta}{\alpha+\beta} m}{p_2}
\end{align*}
$$

也就是说 $\frac{\alpha}{\alpha+\beta}$ 比例的预算用于购买 $x_{1}$，$\frac{\beta}{\alpha+\beta}$ 比例的预算用于购买 $x_{2}$

Cobb-Douglas 函数是一种 [[微观经济学/数理经济学/位似函数\|位似函数]]，其特征是：

1. 所有商品需求的收入弹性均为 1
2. 所有商品的的平均消费倾向（average propensity to consume, APC）和边际消费倾向（marginal propensity to consume, MPC）为常数：

$$
\begin{align}
APC_{1}&\equiv\frac{p_{1}x_{1}}{m}=\frac{\alpha}{\alpha+\beta}=\frac{\partial p_{1}x_{1}}{\partial m}\equiv MPC_{1} \\
APC_{2}&\equiv\frac{p_{2}x_{2}}{m}=\frac{\beta}{\alpha+\beta}=\frac{\partial p_{2}x_{2}}{\partial m}\equiv MPC_{2}
\end{align}
$$

这符合代表性消费者的特征。

### Code

```python
import sympy as sp
x1,x2,a,b,p1,p2,m,la=sp.symbols('x_{1},x_{2},\\alpha,\\beta,p_{1},p_{2},m,\lambda',real=True)
u=x1**a*x2**b
g=m-(p1*x1+p2*x2)
L=u+la*g
FOC=[sp.diff(L,i) for i in [x1,x2,la]]
df=sp.solve(FOC,[x1,x2,la],dict=True)
dx1=sp.Eq(x1,df[0][x1])
dx2=sp.Eq(x2,df[0][x2])
print(sp.latex(dx1),sp.latex(dx2),sep='\n')
```

## 支出最小化

$$
\begin{align*}
\min&\ p_1 x_1+p_2 x_2 \\
\text{s.t.}&\ x_1^\alpha x_2^\beta=\bar{u}
\end{align*}
$$

The Lagrangian of this problem is

$$
L=p_1 x_1+p_2 x_2+\mu(\bar{u}-x_1^\alpha x_2^\beta)
$$

F.O.C

$$
\begin{align*}
\frac{\partial L}{\partial x_1}&=p_1-\mu \alpha x_1^{\alpha-1}x_2^\beta=0 \\
\frac{\partial L}{\partial x_2}&=p_2-\mu \beta x_1^{\alpha}x_2^{\beta-1}=0
\end{align*}
$$

which implies

$$
\frac{p_1x_1}{p_2x_2}=\frac{\alpha}{\beta}
$$

代入预算约束解得 [[微观经济学/希克斯需求函数\|希克斯需求函数]]（解法同下文成本最小化一节）

$$
\begin{align*}
x_{1}^{H}&=\bar{u}^{\frac{1}{\alpha+\beta}}\left(\frac{\alpha/\beta}{p_{1}/p_{2}}\right)^{\frac{\beta}{\alpha+\beta}} \\
x_{2}^H&=\bar{u}^{\frac{1}{\alpha+\beta}}\left(\frac{p_{1}/p_{2}}{\alpha/\beta}\right)^{\frac{\alpha}{\alpha+\beta}}
\end{align*}
$$

## 利润最大化

$$
\max_{x_i}\ px_1^\alpha x_2^\beta-(w_1x_1+w_2x_2)
$$

F.O.C.

$$
\begin{align*}
p\alpha x_1^{\alpha-1}x_2^\beta-w_1&=0 \\
p\beta x_1^\alpha x_2^{\beta-1}-w_2&=0
\end{align*}
$$

which implies

$$
\frac{w_1x_1}{w_2x_2}=\frac{\alpha}{\beta}
$$

这个方程直接求解比较困难，可以先将 F.O.C.转化为对数形式

$$
\begin{align}
(\alpha-1)\ln x_{1}+\beta \ln x_{2} & =\ln w_{1}-\ln\alpha-\ln p \\
\alpha \ln x_{1}+(\beta-1)\ln x_{2} & =\ln w_{2}-\ln\beta-\ln p
\end{align}
$$

这就得到了关于变量 $\ln x_{1}$ 和 $\ln x_{2}$ 的线性方程组，其扩展矩阵为

$$
\begin{bmatrix}
(\alpha-1) & \beta & \ln w_{1}-\ln\alpha-\ln p \\
\alpha & \beta-1 & \ln w_{2}-\ln\beta-\ln p
\end{bmatrix}
$$

根据 Cramer's Law 可得

$$
\begin{align}
(1-\alpha-\beta)\ln x_{1} & =(\beta-1)(\ln w_{1}-\ln\alpha-\ln p)-\beta(\ln w_{2}-\ln\beta-\ln p) \\
(1-\alpha-\beta)\ln x_{2} & =(\alpha-1)(\ln w_{2}-\ln\beta-\ln p)-\alpha(\ln w_{1}-\ln\alpha-\ln p)
\end{align}
$$

初步化简

$$
\begin{align}
(1-\alpha-\beta)\ln x_{1} & =(\beta-1)\left( \ln \frac{w_{1}}{\alpha}\right)-\beta\left( \ln \frac{w_{2}}{\beta}\right)+\ln p \\
(1-\alpha-\beta)\ln x_{2} & =(\alpha-1)\left( \ln \frac{w_{2}}{\beta}\right)-\alpha\left( \ln \frac{w_{1}}{\alpha}\right)+\ln p
\end{align}
$$

继续化简

$$
\begin{align}
(1-\alpha-\beta)\ln x_{1} & =\ln\left[ p\frac{\left( \frac{w_{1}}{\alpha} \right)^{\beta-1}}{\left( \frac{w_{2}}{\beta} \right)^\beta}  \right] \\
(1-\alpha-\beta)\ln x_{2} & =\ln\left[ p\frac{\left( \frac{w_{2}}{\beta} \right)^{\alpha-1}}{\left( \frac{w_{1}}{\alpha} \right)^\alpha}  \right]
\end{align}
$$

最终可得**要素需求函数**

$$
\begin{align}
x_{1}^* & =\left[ p\frac{\left( \frac{w_{1}}{\alpha} \right)^{\beta-1}}{\left( \frac{w_{2}}{\beta} \right)^\beta}  \right]^{\frac{1}{1-\alpha-\beta}} \\
x_{2}^* & =\left[ p\frac{\left( \frac{w_{2}}{\beta} \right)^{\alpha-1}}{\left( \frac{w_{1}}{\alpha} \right)^\alpha}  \right]^{\frac{1}{1-\alpha-\beta}}
\end{align}
$$

> 注意：当 $\alpha+\beta=1$ 即规模报酬不变时，要素需求无限大，这意味着厂商的规模无法确定。

### 扩展

宏观经济学常用 Cobb-Douglas 函数 $Y=K^\alpha L^{1-\alpha}$ 的紧凑形式：

$$
y=\frac{Y}{L}=\left( \frac{K}{L} \right)^\alpha=k^\alpha
$$

利润最大化问题为

$$
\max_{k} pk^\alpha-(rk+w)
$$

F.O.C.仅有单个条件

$$
p\alpha k^{\alpha-1}=r
$$

将其代回目标函数后需要结合**竞争性条件**（零利润）得到第二条件

$$
(1-\alpha)pk^\alpha=w
$$

## 成本最小化

$$
\begin{align*}
\min_{x_i}&\ w_1x_1+w_2x_2 \\
\text{s.t.}&\ x_1^{\alpha}x_2^{\beta}=q \\
\end{align*}
$$

The Lagrangian for this problem is

$$
L=w_1x_1+w_2x_2+\lambda(q-x_{1}^{\alpha}x_{2}^\beta)
$$

F.O.C

$$
\begin{align*}
\frac{\partial L}{\partial x_{1}}=w_{1}-\lambda \alpha x_{1}^{\alpha-1}x_{2}^{\beta}=0\\
\frac{\partial L}{\partial x_{2}}=w_{2}-\lambda \beta x_{1}^{\alpha}x_{2}^{\beta-1}=0
\end{align*}
$$

which implies

$$
\frac{w_{1}x_{1}}{w_{2}x_{2}}=\frac{\alpha}{\beta}
$$

这个方程直接求解比较困难，可以先将约束条件和上述条件转化为对数形式

$$
\begin{align}
\alpha \ln x_{1}+\beta \ln x_{2} & =\ln q \\
\ln x_{1}-\ln x_{2} & =\ln \frac{\alpha}{\beta}-\ln \frac{w_{1}}{w_{2}}
\end{align}
$$

这就得到了关于变量 $\ln x_{1}$ 和 $\ln x_{2}$ 的线性方程组，其扩展矩阵为

$$
\begin{bmatrix}
\alpha & \beta & \ln q \\
1 & -1 & \ln \frac{\alpha}{\beta}-\ln \frac{w_{1}}{w_{2}}
\end{bmatrix}
$$

根据 Cramer's Law 可得

$$
\begin{align}
(-\alpha-\beta)\ln x_{1} & =-\ln q-\beta \ln \left( \frac{\alpha/\beta}{w_{1}/w_{2}} \right) \\
(-\alpha-\beta)\ln x_{2} & =-\ln q+\alpha \ln \left( \frac{\alpha/\beta}{w_{1}/w_{2}} \right)
\end{align}
$$

最终可得**条件要素需求函数**

$$
\begin{align*}
x_{1}^{c}&=q^{\frac{1}{\alpha+\beta}}\left(\frac{\alpha/\beta}{w_{1}/w_{2}}\right)^{\frac{\beta}{\alpha+\beta}} \\
x_2^c&=q^{\frac{1}{\alpha+\beta}}\left(\frac{w_{1}/w_{2}}{\alpha/\beta}\right)^{\frac{\alpha}{\alpha+\beta}}
\end{align*}
$$

## 边际成本

边际成本是最重要的厂商特征，标准的求解路径为：成本最小化→条件要素需求函数→成本函数→边际成本，然而这一路径过于繁琐。因此，了解如何从生产函数“直达”边际成本很有帮助。

[[微观经济学/成本最小化\|成本最小化]] 问题为

$$
\begin{align*}
\min_{x_i}&\ w_1x_1+w_2x_2 \\
\text{s.t.}&\ x_1^{\alpha}x_2^{\beta}=q \\
\end{align*}
$$

根据生产平衡等式可得方程组

$$
\begin{align}
MC & =\frac{w_{1}}{MP_{1}} \\
MC & =\frac{w_{2}}{MP_{2}}
\end{align}
$$

已知成本函数变量包含 $q$，故通过边际产出引入可得

$$
\begin{align}
MP_{1} & =\alpha x_{1}^{\alpha-1}x_{2}^\beta=\frac{\alpha q}{x_{1}} \\
MP_{2} & =\beta x_{1}^\alpha x_{2}^{\beta-1}=\frac{\beta q}{x_{2}}
\end{align}
$$

代回生产平衡等式得到

$$
\begin{align}
x_{1} & =\frac{\alpha q}{w_{1}}MC \\
x_{2} & =\frac{\beta q}{w_{2}}MC
\end{align}
$$

代入约束条件得解

$$
\begin{align}
\left( \frac{\alpha q}{w_{1}}MC \right)^\alpha \left( \frac{\beta q}{w_{2}}MC \right)^\beta & =q \\
\left( \frac{\alpha}{w_{1}} \right)^\alpha\left( \frac{\beta}{w_{2}} \right)^\beta MC^{\alpha+\beta} & =q^{1-\alpha-\beta} \\
MC & =q^{\frac{1-\alpha-\beta}{{\alpha+\beta}}} \left( \frac{w_{1}}{\alpha} \right)^{\frac{\alpha}{\alpha+\beta}} \left( \frac{w_{2}}{\beta} \right)^{\frac{\beta}{\alpha+\beta}}
\end{align}
$$
