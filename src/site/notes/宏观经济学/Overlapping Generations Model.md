---
{"dg-publish":true,"permalink":"/宏观经济学/Overlapping Generations Model/","created":"2024-10-12T10:24:43.000+08:00","updated":"2024-10-12T10:24:43.000+08:00"}
---



## 分散经济

- 时间是无限且离散的
- 个体只存活两期（$t$ 期出生的个体存活于 $t$ 期和 $t+1$ 期）

个体：
- 个体在第一期供给 1 单位劳动并获得工资 $w(t)$，用于消费 $c_{1}(t)$ 和储蓄 $s(t)$
- 个体在第二期使用第一期储蓄所得的本息 $[1+r(t+1)]s(t)$ 进行消费 $c_{2}(t+1)$

厂商：see [[宏观经济学/Ramsey-Cass-Koopmans Model#厂商\|Ramsey-Cass-Koopmans Model#厂商]]
$$
\begin{align}
R(t) & =f'(k(t)) \\
w(t) & =f(k(t))-kf'(k(t))
\end{align}
$$
市场出清：
$$
1+r(t)  R(t) 
$$
个体效用最大化问题为
$$
\begin{align}
\max_{\{ c_{1}(t),c_{2}(t+1),s(t) \}} &\ u(c_{1}(t))+\beta u(c_{2}(t+1)) \\
\text{s.t.} &\ c_{1}(t)+s(t)\leq w(t) \\
&\ c_{2}(t+1)\leq [1+r(t+1)]s_{t}
\end{align}
$$
$u(\cdot)$ 关于 $c$ 是严格递增的，因此约束条件取等号，问题等价于
$$
\begin{align}
\max_{\{ c_{1}(t),c_{2}(t+1),s(t) \}} &\ u(c_{1}(t))+\beta u(c_{2}(t+1)) \\
\text{s.t.} &\ c_{1}(t)+\frac{c_{2}(t+1)}{1+r(t+1)}= w(t) 
\end{align}
$$
Lagrangian 函数为
$$
\mathcal{L}=u(c_{1}(t))+\beta u(c_{2}(t+1))+\lambda \left[ w(t)-c_{1}(t)-\frac{c_{2}(t+1)}{1+r(t+1)} \right]
$$
F.O.C.
$$
\begin{align}
\frac{\partial \mathcal{L}}{\partial c_{1}(t)} & =u'(c_{1}(t))-\lambda=0 \\
\frac{\partial \mathcal{L}}{\partial c_{2}(t+1)} & =\beta u'(c_{2}(t+1))-\lambda \frac{1}{1+r(t+1)}=0
\end{align}
$$
整理得**欧拉方程**
$$
\frac{u'(c_{1}(t))}{u'(c_{2}(t+1))} = \beta[1+r(t+1)]
$$
从而解得
$$
s(t)=s(w(t),R(t+1))
$$
**注意**：可以证明，稳态时储蓄率 $s^*=\frac{\partial s(t)}{\partial w(t)}$ 和 [[宏观经济学/Solow Model\|Solow Model]] 一样为常数。

资本的动态方程为
$$
K(t+1)=L(t)s(t)=L(t)s(w(t),R(t+1))
$$

其中 $L(t)\equiv(1+n)^tL(0)$ ，等式两边除以 $L(t+1)=(1+n)L(t)$ 得
$$
k(t+1)=\frac{s(w(t),R(t+1))}{1+n}
$$
> [!NOTE]
> 如果考虑技术进步，资本动态方程为
> $$
> K(t+1)=A(t)L(t)s(t)
> $$
> 等式两边除以 $A(t+1)=(1+g)A(t)$ 得
> $$
> k(t+1)=\frac{s(w(t),R(t+1))}{(1+n)(1+g)}
> $$

代入厂商最优条件以及稳态条件 $k^*=k(t+1)=k(t)$ 得
$$
k^*=\frac{s(f(k^*)-k^*f'(k^*),f'(k^*))}{1+n}
$$
## 实例一

假设效用函数形式为
$$
U=\frac{c_{1}(t)^{1-\theta}-1}{1-\theta}+\beta \frac{c_{2}(t+1)^{1-\theta}-1}{1-\theta}
$$
欧拉方程为
$$
\left[ \frac{c_{1}(t)}{c_{2}(t+1)} \right]^{-\theta}=\beta R(t+1)
$$
代入约束条件求解 $s(t)$
$$
\begin{align}
\left[ \frac{w(t)-s(t)}{R(t+1)s(t)} \right]^{-\theta} & =\beta R(t+1) \\
s(t) & = \frac{w(t)}{\phi(t+1)}
\end{align}
$$
其中 $\phi(t+1)\equiv \left[ 1+\beta^{-\frac{1}{\theta}} R(t+1)^{\frac{\theta-1}{\theta}}\right]>1$

假设生产函数形式为 $F(K,L)=K^\alpha L^{1-\alpha}\implies f(k)=k^\alpha$，最优化条件为
$$
\begin{align}
w(t)  & =(1-\alpha)k^\alpha \\
R(t) & =\alpha k^{\alpha-1}
\end{align}
$$
资本动态方程为
$$
k(t+1)=\frac{w(t)}{(1+n)\phi(t+1)}
$$
代入厂商最优条件以及稳态条件得
$$
k^* =\frac{(1-\alpha) (k^*)^{\alpha}}{(1+n)\left[ 1+\beta^{-\frac{1}{\theta}} \alpha^{\frac{\theta-1}{\theta}}(k^*)^{(\alpha-1)\frac{\theta-1}{\theta}}\right]}
$$
## 实例二
假设效用函数形式为
$$
U=\ln c_{1}(t)+\beta \ln c_{2}(t+1)
$$
欧拉方程为
$$
\frac{c_{2}(t+1)}{c_{1}(t)}=\beta R(t+1)
$$
代入约束条件求解 $s(t)$
$$
\begin{align}
\frac{R(t+1)s(t)}{w(t)-s(t)}&=\beta R(t+1) \\
s(t) & =\frac{\beta}{1+\beta}w(t)
\end{align}
$$
假设生产函数形式为 $F(K,AL)=K^\alpha (AL)^{1-\alpha}\implies f(k)=k^\alpha$，最优化条件为
$$
\begin{align}
w(t)  & =(1-\alpha)k^\alpha \\
R(t) & =\alpha k^{\alpha-1}
\end{align}
$$
资本动态方程为
$$
k(t+1)=\frac{\frac{\beta}{1+\beta}w(t)}{(1+n)(1+g)}
$$
代入厂商最优条件以及稳态条件得
$$
k^*=\frac{\frac{\beta}{1+\beta}(1-\alpha)(k^*)^\alpha}{(1+n)(1+g)}\implies k^*=\left[ \frac{\beta(1-\alpha)}{(1+\beta)(1+n)(1+g)} \right]^{\frac{1}{1-\alpha}}
$$
> [!NOTE]
> 对比 [[宏观经济学/Solow Model\|Solow Model]] 的结果
> $$
> s(k^*)^\alpha=(n+g+\delta)k^* \implies  k^*=\left[ \frac{s}{n+g+\delta} \right]^{\frac{1}{1-\alpha}}
> $$
> 这里的储蓄率 $s$ 对应实例二当中的 $\frac{\beta}{1+\beta}$，可见二者非常相似；实际上实例二的结果和离散 Solow Model 完全相同。

## 社会计划者经济

社会计划者最优化问题为
$$
\begin{align}
\max &\ \sum\limits_{t=1}^{\infty} \beta_{s}^t[u(c_{1}(t))+\beta u(c_{2}(t+1))] \\
\text{s.t.} &\ F(K(t),L(t))=K(t+1)+L(t)c_{1}(t)+L(t-1)c_{2}(t)
\end{align}
$$
最终解得欧拉方程为
$$
\frac{u'(c_{1}(t))}{u'(c_{2}(t+1))} = \beta f'(k(t+1))
$$
相当于将利润最大化条件代入分散经济的欧拉方程，因此分散经济并无效率损失。

在预算约束等式两边除以 $L(t)=(1+n)L(t-1)$ 后取稳态
$$
\begin{align}
\frac{F(K(t),L(t))}{L(t)} & =\frac{L(t+1)}{L(t)} \frac{K(t+1)}{L(t+1)}+c_{1}(t)+\frac{c_{2}(t)}{1+n} \\
f(k^*)-(n+1)k^* & =c_{1}^*(t)+\frac{c_{2}^*}{1+n}\equiv c^* \\
\end{align}
$$
我们将等式右侧定义为跨期总消费 $c^*$，为使其最大化
$$
\frac{\partial c^*}{\partial k^*}=f'(k^*)-(n+1)=0\implies k^*_{g}=(f')^{-1}(n+1)
$$
因此存在一个资本黄金率 $k^*_{g}$ 以及对应储蓄率 $s^*_{g}$ 使得跨期总消费最大化。
- $[k_{g}^*,\infty)$ 区间属于过度投资， $[s^*_{g},1]$ 区间属于过度储蓄
- 上述范围称为**动态无效率（dynamically inefficient）区间**，不符合帕累托最优


