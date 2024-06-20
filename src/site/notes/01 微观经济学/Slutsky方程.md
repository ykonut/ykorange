---
{"dg-publish":true,"permalink":"/01 微观经济学/Slutsky方程/","created":"2024-06-20T16:02:06.010+08:00","updated":"2024-06-20T16:21:32.709+08:00"}
---

将[[01 微观经济学/支出函数\|支出函数]]代入马歇尔需求-希克斯需求恒等式并对 $p_{j}$ 求导
$$
\frac{\partial x_i^H(\mathbf{p},u)}{\partial p_j}=\frac{\partial x_i^M(\mathbf{p},e(\mathbf{p},\bar{u}))}{\partial p_j}+\frac{\partial x_i^M(\mathbf{p},e(\mathbf{p},\bar{u}))}{\partial e}\frac{\partial e(\mathbf{p},\bar{u})}{\partial p_j}
$$
整理得 **Slutsky 方程**
$$
\frac{\partial x_i^M}{\partial p_j}=\underbrace{ \frac{\partial x_i^H}{\partial p_j} }_{ \text{替代效应} }-\underbrace{ \frac{\partial x^M_i}{\partial m}x_j }_{ \text{收入效应} }
$$
> [!NOTE]
> - 替代效应：补偿消费者的收入直至其效用恢复到 $p_{j}$ 变动前时，消费者需求的变化。
> 
> - 收入效应：若 $p_{j}$ 增加 $1$ ，预算约束变为 $\sum\limits_{i\neq j}^{}p_{i}x_{i}+(p_{j}+1)p_{j}x_{j}=m$，相当于收入减少为 $m-x_{j}$，因此 $-x_{j} \frac{\partial x_{i}^M}{\partial M}$ 就是收入变动产生的效应。
> 
> 对于正常商品，收入效应为正，价格变动对希克斯需求的影响更大（希克斯需求曲线的斜率更小）；对于贫穷商品，收入效应为负，价格变动对希克斯需求的影响更小（希克斯需求曲线的斜率更大）。

可以进一步改写为弹性形式：
$$
\begin{align}
\frac{\partial x_i^M}{\partial p_j} & =\frac{\partial x_i^H}{\partial p_j}-\frac{\partial x^M_i}{\partial m}x_j \\
\frac{\partial x_i^M}{\partial p_j} \frac{p_{j}}{x_{i}} &= \frac{\partial x_i^H}{\partial p_j} \frac{p_{j}}{x_{i}}-\frac{\partial x^M_i}{\partial m} \frac{m}{x_{i}}\frac{p_{j}x_{j}}{m} \\
\varepsilon_{ji}^M & =\varepsilon_{ji}^H-s_{j}\eta_{i}
\end{align}
$$
令 $j=i$ 考察自效应
$$
\varepsilon_{ii}^M =\varepsilon_{ii}^H-s_{i}\eta_{i}
$$
需求定理表明 $\varepsilon_{ii}^H \le 0$，对于大多数正常商品 $\eta_i>0$ 且 $s_i$ 较小，所以 $\varepsilon_{ii}^M<0$；对于平均消费倾向很大的贫穷商品，有可能使得 $\varepsilon_{ii}^M>0$，即 **Giffen 商品**。