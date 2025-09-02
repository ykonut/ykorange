---
{"dg-publish":true,"permalink":"/💰宏观经济学/Barro(1990) Model/","created":"2024-10-12T10:24:52.000+08:00","updated":"2024-10-12T10:24:52.000+08:00"}
---


## 代表性家庭

假设劳动供给是固定常数且标准化为 1，即 $L(t)=\bar{L}=1$

瞬时效用函数为
$$
u(c(t))=\frac{c(t)^{1-\sigma}-1}{1-\sigma} 
$$
目标函数为
$$
U(0)=\int_{0}^{\infty} e^{-\rho t}u(c(t))\bar{L} dt \quad (\rho>0)
$$
资产的动态方程为
$$
\dot{\mathcal{A}}(t)\equiv (1-\tau)[r(t)\mathcal{A}(t)+w(t)\bar{L}]-c(t)\bar{L}
$$
其中，人均资产定义为
$$
a(t)\equiv \frac{\mathcal{A}(t)}{\bar{L}}\implies \dot{\mathcal{A}(t)}=\frac{\mathrm{d} a(t)\bar{L}}{\mathrm{d} t}=\dot{a}(t)\bar{L}
$$
从而得到：
$$
\dot{a}(t)=(1-\tau)[r(t)a(t)+w(t)]-c(t)
$$
综上所属，家庭最优化问题为
$$
\begin{align}
\max_{c(t)} &\ \int_{0}^{\infty} \frac{c(t)^{1-\sigma}-1}{1-\sigma} e^{-\rho t} \, \mathrm{d}t \\
\text{s.t.} &\ \dot{a}(t)=(1-\tau)[r(t)a(t)+w(t)]-c(t) \\
&\ \lim_{t\to \infty}a(t)\exp\left[ -\int_{0}^{t} (r(s)-n) \, \mathrm{d}s  \right]\geq 0
\end{align}
$$
Set up the current-value Hamiltonian function
$$
\hat{H}(a,c,\mu)=\frac{c(t)^{1-\sigma}-1}{1-\sigma}+\mu(t)\{(1-\tau)[r(t)a(t)+w(t)]-c(t)\}
$$
Maximum Principle
$$
\begin{align}
\frac{\partial \hat{H}(a,c,\mu)}{\partial c} & =0 &\implies& c(t)^{-\sigma}=\mu(t) \tag{1}\\
\frac{\partial \hat{H}(a,c,\mu)}{\partial a} & = -\dot{\mu}(t)+\rho \mu(t) &\implies& \frac{\dot{\mu}(t)}{\mu(t)}=\rho-(1-\tau)r(t) \tag{2}\\
\frac{\partial \hat{H}(a,c,\mu)}{\partial \mu}&=\dot{a}(t) \tag{3}\\
\lim_{t\to \infty}[e^{-\rho t}\mu(t)a(t)] & =0 \tag{4}
\end{align}
$$
根据(1)可得
$$
-\sigma \ln[c(t)]=\ln[\mu(t)]\implies -\sigma\frac{ \dot{c}(t)}{c(t)}=\frac{\dot{\mu}(t)}{\mu(t)}
$$
结合(2)得到欧拉方程
$$
\frac{\dot{c}(t)}{c(t)}=\frac{(1-\tau)r(t)-\rho}{\sigma}
$$
## 代表性企业

代表性企业生产函数为
$$
y(t)=Ak(t)^\alpha g(t)^{1-\alpha}
$$
其中，政府支出为
$$
g(t)=\tau y(t)
$$
利润最大化问题为
$$
\max Ak(t)^\alpha g(t)^{1-\alpha}-R(t)k(t)-w(t)
$$
F.O.C.
$$
\begin{align}
A\alpha k(t)^{\alpha-1}g(t)^{1-\alpha} & =R(t) \\
Ak(t)^\alpha g(t)^{1-\alpha}-A\alpha k(t)^{\alpha}g(t)^{1-\alpha} & =w(t)
\end{align}
$$
根据 [[⚖️微观经济学/数理经济学/Cobb-Douglas函数\|Cobb-Douglas函数]]的性质可知
$$
\frac{R(t)k(t)}{w(t)}=\frac{\alpha}{1-\alpha}
$$
以及
$$
\begin{align}
k^*(t) & =\frac{\alpha y(t)}{R(t)} \\
1 & =\frac{(1-\alpha)y(t)}{w(t)}
\end{align}
$$
## 均衡

现在我们已经有资产动态恒等式和边际产出恒等式，此外：

政府平衡预算恒等式为
$$
\tau(r(t)a(t)+w(t))=g(t)
$$
市场出清恒等式为
$$
\begin{align}
a(t) & =k(t) \\
r(t) & =R(t)
\end{align}
$$
利用恒等式消去资本动态方程中的变量得到变量关系式
$$
\begin{align}
\dot{k}(t) & =(1-\tau)[r(t)k(t)+w(t)]-c(t) \\
 & =(1-\tau)[\alpha y(t)+(1-\alpha)y(t)]-c(t) \\
 & =y(t)-g(t)-c(t)
\end{align}
$$
利用恒等式消去欧拉方程中的变量得到数值解
$$
\begin{align}
\frac{\dot{c}(t)}{c(t)} & =\frac{(1-\tau)r(t)-\rho}{\sigma} \\
 &= \frac{(1-\tau)A\alpha k(t)^{\alpha-1}g(t)^{1-\alpha}-\rho}{\sigma}
\end{align}
$$
其中 $\frac{g(t)}{k(t)}$ 可以通过消去生产函数中的产量得到
$$
\begin{align}
g(t) & =\tau Ak(t)^\alpha g(t)^{1-\alpha} \\
\left[ \frac{g(t)}{k(t)} \right]^\alpha & =\tau A
\end{align}\implies \left[ \frac{g(t)}{k(t)} \right]^{1-\alpha}=(\tau A)^{\frac{1-\alpha}{\alpha}}
$$
代入欧拉方程得到数值解
$$
\frac{\dot{c}(t)}{c(t)}=\frac{(1-\tau)A\alpha (\tau A)^{\frac{1-\alpha}{\alpha}}-\rho}{\sigma}
=\frac{\alpha (1-\tau)A^{\frac{1}{\alpha}}\tau^{\frac{1-\alpha}{\alpha}}-\rho}{\sigma}
$$

## 政策分析

求使得增长率最大化的税率 $\tau$
$$
\begin{align}
\frac{\partial \cdot}{\partial \tau}&=\frac{\alpha A^{\frac{1}{\alpha}}}{\sigma}\left[ -\tau^{\frac{1-\alpha}{\alpha}}+\frac{1-\alpha}{\alpha}(1-\tau)\tau^{\frac{1-\alpha}{\alpha}-1} \right] \\
 & =\frac{\alpha A^{\frac{1}{\alpha}}}{\sigma}\tau^{\frac{1-\alpha}{\alpha}}\left[ -1+\frac{1-\alpha}{\alpha}\frac{1-\tau}{\tau} \right] \\
&=\frac{\alpha A^{\frac{1}{\alpha}}}{\sigma}\tau^{\frac{1-\alpha}{\alpha}} \frac{1}{\alpha \tau} \left[ -\alpha \tau+(1-\tau-\alpha+\alpha \tau)\right] \\
&=\frac{\alpha A^{\frac{1}{\alpha}}}{\sigma}\tau^{\frac{1-\alpha}{\alpha}}  \frac{1-\tau-\alpha}{\alpha \tau}
\end{align}
$$
令上式等于零得到最优税率 $\tau^*=1-\alpha$，且
$$
\begin{cases}
\frac{\partial \cdot}{\partial \tau}>0 &\text{if } \tau<1-\alpha \\
\frac{\partial \cdot}{\partial \tau}<0 &\text{if } \tau>1-\alpha 
\end{cases}
$$
所以这是唯一的最优税率。

我们回顾一下背后的机制：
- 负向机制：减少收入→减少投资 $\dot{a}$ →减少资产 $k$ →减少产出 $y$
- 正向机制：增加 $g$ →增加产出 $y$ 

## 外部性

在分散经济模型中，厂商自认为无法影响政府投资，因此私人边际产出为
$$
MPP_{k}=\left.\frac{\partial y(t)}{\partial k(t)}\right|_{g(t)=g(t)}=A\alpha k(t)^{\alpha-1}g(t)^{1-\alpha}=\alpha (1-\tau)A^{\frac{1}{\alpha}}\tau^{\frac{1-\alpha}{\alpha}}
$$
因此社会边际产出为
$$
MSP_{k}=\left.\frac{\partial y(t)}{\partial k(t)}\right|_{g(t)=\tau y(t)}=A^{\frac{1}{\alpha}}\tau^{\frac{1-\alpha}{\alpha}}
$$
> [!NOTE]
> 在生产函数中消去政府支出得到的就是社会生产函数（形式类似 [[💰宏观经济学/AK Model\|AK Model]]）
> $$
> \begin{align}
> y(t) & =Ak(t)^\alpha \tau^{1-\alpha}y(t)^{1-\alpha} \\
> y(t)^\alpha & =Ak(t)^\alpha \tau^{1-\alpha} \\
> y(t) & =A^{\frac{1}{\alpha}}\tau^{\frac{1-\alpha}{\alpha}}k(t)
> \end{align}
> $$

显然 MPP 低于 MSP，相应地分散经济增长率低于社会计划者经济。
