---
{"dg-publish":true,"permalink":"/宏观经济学/AK Model/","created":"2025-09-12 18:58","updated":"2025-11-22 17:29"}
---


AK 生产函数通过放松边际产出递减和稻田条件假设避免了稳态，类比 [[宏观经济学/Solow Model\|Solow Model]]：

$$
g_{k}\equiv\frac{\dot{k}}{k}=\frac{s f(k)}{k}-(n+g+\delta)
$$

通过将生产函数设定为 $Y=AK$，就能得到 $g_{k}=sA-(n+g+\delta)$ 的不变增长率。

当然，这种对比并不严谨。下面讨论的 AK Model 排除了外生技术增长率，结合了 [[宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] 的内生储蓄率，但核心结论就是得出不变增长率。

## 基本假设

偏好

$$
U=\int_{0}^{\infty} e^{-(\rho-n)t} \frac{c^{1-\theta}-1}{1-\theta}\, \mathrm{d}t
$$

**注意**：上式蕴含 $L(t)=L(0)e^{nt}$ 以及 $L(0)=1$；see also [[微观经济学/风险规避系数#CRRA 效用函数\|风险规避系数#CRRA 效用函数]]

预算约束

$$
\dot{a}(t)=(r(t)-n)a(t)+w(t)-c(t)
$$

No-Ponzi game 约束

$$
\lim_{t\to \infty}a(t)\exp\left[ -\int_{0}^{t} (r(s)-n) \, \mathrm{d}s  \right]\geq 0
$$

欧拉方程

$$
\frac{\dot{c}(t)}{c(t)}=\frac{r(t)-\rho}{\theta}
$$

横截条件

$$
\lim_{t\to \infty}\left[ a(t)\exp\left( -\int_{0}^{t} (r(s)-n) \, \mathrm{d}s  \right) \right]=0
$$

最终产品的生产函数设定为

$$
Y(t)=AK(t)\implies y(t)=Ak(t)
$$

这一设定违反了 [[宏观经济学/Solow Model\|Solow Model]] 中的假设②和③，即 $f''(k)=0$ 和 $\lim\limits_{t\to0}f'(k)=A>0$

要素市场出清

$$
\begin{align}
f'(k(t)) & =R(t) \\
0 & =w(t)
\end{align}
$$

**注意**：显然 $R(t)\equiv A$ ；生产函数仅和资本相关，因此劳动的报酬退化为 0

借贷市场出清

$$
\begin{align}
a(t) & =k(t) \\
r(t) & =R(t)-\delta
\end{align}
$$

> 除了假定 $Y=AK$ 以外，和 [[宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] 基本一致。

## 均衡

根据预算约束和市场出清条件可得**资本的动态方程**

$$
\dot{k}(t)=(A-\delta-n)k(t)-c(t)
$$

根据欧拉方程和市场出清条件可得**消费的动态方程**

$$
\frac{\dot{c}(t)}{c(t)}=\frac{[f'(k(t))-\delta]-\rho}{\theta}=\frac{A-\delta-\rho}{\theta}
$$

根据横截条件和市场出清条件可得固定利率形式

$$
\lim_{t\to \infty}\left[ k(t)e^{-(A-\delta-n)t} \right]=0
$$

上述结果与 [[宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] 相比最突出的是，消费增长率为常数，与资本存量 $k(t)$ 无关，甚至可以直接求出 $c(t)$ 的路径（see [[Math&Stats/常微分方程\|常微分方程]] ）：

$$
c(t)=c(0)\exp\left[ \frac{1}{\theta}(A-\delta-\rho)t \right]
$$

因此，这个模型没有稳态也不存在转移动态（transitional dynamics）。

将 $c(t)$ 的路径代入资本的动态方程也就可以得到 $k(t)$ 的路径：

$$
\dot{k}(t)=(A-\delta-n)k(t)-c(0)\exp\left[ \frac{1}{\theta}(A-\delta-\rho)t \right]
$$

这个微分方程的解结合横截条件（过程比较复杂）可得

$$
k(t)=k(0)\exp\left[ \frac{1}{\theta}(A-\delta-\rho)t \right]
$$

总之，**消费、资本和产出的增长率**是一样的，均为 $g^*=\frac{A-\delta-\rho}{\theta}$；作为对比，[[宏观经济学/Solow Model\|Solow Model]] 得出的经济增长率 $n+g$ 完全来自外生参数，而 AK model 将增长内生化了。

均衡的储蓄率为

$$
\begin{align}
s & =\frac{\dot{K}(t)+\delta K(t)}{Y(t)} \\
 & =\frac{\dot{K}(t)/K(t)+\delta}{Y(t)/K(t)} \\
 & =\frac{\dot{k}(t)/k(t)+n+\delta}{A} \\
 & =\frac{\frac{1}{\theta}(A-\delta-\rho)+n+\delta}{A} \\
 & =\frac{A-\rho+\theta n+(\theta-1)\delta}{\theta A}
\end{align}
$$

其中

$$
\frac{\dot{K}(t)}{K(t)}=\frac{\mathrm{d} \ln L(t)k(t)}{\mathrm{d} t} =\frac{\dot{k}(t)}{k(t)}+n
$$

因此，均衡储蓄率和 [[宏观经济学/Solow Model\|Solow Model]] 以及 [[宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] 一样为常数。

## 政策分析

假如考虑政府征收比例为 $\tau$ 的资本利得税，则预算约束变为

$$
\dot{a}(t)=[(1-\tau)r(t)-n]a(t)+w(t)-c(t)
$$

增长率变为

$$
g^*=\frac{(1-\tau)(A-\delta)-\rho}{\theta}
$$

储蓄率变为

$$
s=\frac{(1-\tau)A-\rho+\theta n+(1-\tau-\theta)\delta}{\theta A}
$$

如果 $A-\delta>0$（相当于利率 $r(t)$ 为正），则上式关于 $\tau$ 递减。
