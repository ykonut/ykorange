---
{"dg-publish":true,"permalink":"/02 宏观经济学/Romer(1986) Model/","created":"2024-06-18T19:39:34.000+08:00","updated":"2024-06-18T19:39:34.000+08:00"}
---


该模型和 [[02 宏观经济学/AK Model\|AK Model]] 本质相同，只是通过所谓 Learning by Doing 合理化生产函数。

假设总量生产函数满足新古典特征：
$$
Y(t)=K(t)^\alpha [A(t)L(t)]^{1-\alpha} \quad \text{where } 0<\alpha<1 \tag{1}
$$
其中 $\frac{\dot{L}(t)}{L(t)}\equiv n$ ，而知识 $A(t)$ 源于**总量资本**积累
$$
A(t)=BK(t)^{\phi}\quad \text{where } B,\phi>0 \tag{2}
$$
结合(1)(2)可得总量生产函数为
$$
Y(t)=B^{1-\alpha}K(t)^{\alpha+\phi(1-\alpha)}L(t)^{1-\alpha}
$$
为了简化，假设储蓄率是外生的，且折旧率为零，**资本的动态方程**为
$$
\dot{K}(t)=sY(t)=s B^{1-\alpha}K(t)^{\alpha+\phi(1-\alpha)}L(t)^{1-\alpha}
$$
> [!NOTE]
> 不同于 [[02 宏观经济学/Solow Model\|Solow Model]]，这里令 $\dot{K}(t)=0$ 不能得到稳态，进而应该尝试令 $\dot{g}_{K}=0$ 找到（二阶）稳态。

先构造对数资本增长率
$$
\begin{align}
g_{K} & \equiv \frac{\dot{K}(t)}{K(t)}=sB^{1-\alpha} K(t)^{(\phi-1)(1-\alpha)} L(t)^{1-\alpha} \\
\ln g_{K} & =\ln(sB^{1-\alpha})+(\phi-1)(1-\alpha)\ln[K(t)]+(1-\alpha)\ln[L(t)] \\
\frac{\dot{g}_{K}}{g_{K}}  & = (\phi-1)(1-\alpha) \frac{\dot{K}(t)}{K(t)}+(1-\alpha) \frac{\dot{L}(t)}{L(t)}
\end{align}
$$

解得**资本增长率的动态方程**
$$
\dot{g}_{K}=(\phi-1)(1-\alpha)g_{K}^{2}+(1-\alpha)ng_{K}
$$
令 $\dot{g}_{K}=0$ 得到
$$
g_{K}^*=\frac{n}{1-\phi}
$$
注意到方程 $\dot{g}_{K}(g_{K})$ 是一个过原点的二次函数，对称轴为 $g_{K}=\frac{n}{2(1-\phi)}$
- $\phi>1$，抛物线开口向上，对称轴小于零，爆炸式增长（没有稳态）；
- $\phi<1$，抛物线开口向下，对称轴大于零，稳态取决于人口增长率；
- $\phi=1,n>0$，退化为过原点的直线，爆炸式增长（没有稳态）；
- $\phi=1,n=0$，退化为 [[02 宏观经济学/AK Model\|AK Model]]，资本增长率为常数(即 $g_{K}=sA$)

对比 $Y(t)=B^{1-\alpha}K(t)L(t)^{1-\alpha}$ 和 $Y(t)=AK(t)$ 的系数可知
- $B^{1-\alpha}L(0)^{1-\alpha}$ 相当于技术因子 $A$
- 资本增长率为 $g_{K}=sB^{1-\alpha}L(0)^{1-\alpha}$
- 如果进一步纳入 [[02 宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] 并考虑折旧
$$
g^*=\frac{B^{1-\alpha}L(0)^{1-\alpha}-\delta-\rho}{\theta}
$$
## 增长核算

根据稳态资本增长率和知识生产函数可以得到知识增长率
$$
\begin{align}
\ln A(t) & =\ln B+\phi \ln K(t) \\
\frac{\mathrm{d} \ln A(t)}{\mathrm{d} t} & =\phi \frac{\mathrm{d} \ln K(t)}{\mathrm{d} t} \\
g_{A}&= \phi g_{K}  
\end{align}\implies g_{A}^*=\frac{\phi n}{1-\phi}
$$
类似地，根据总量生产函数可得
$$
g_{Y}^*=\alpha g_{K}^*+(1-\alpha)(g_{A}^*+g_{L})
$$
## 外部性

为了简化，下面仅考察 $\phi=1,n=0$ 的情形，令 $L(t)=L$

个体生产函数为
$$
Y_{i}(t)=K_{i}(t)^\alpha [A(t)L_{i})]^{1-\alpha} \quad \text{where } 0<\alpha<1 \tag{3}
$$
其中，知识 $A(t)$ 源于**总量资本**积累
$$
A(t)=BK(t)\quad \text{where } B>0 \tag{2}
$$
结合(2)(3)可得个体生产函数为
$$
Y_{i}(t)=B^{1-\alpha}K(t)^{1-\alpha} K_{i}(t)^\alpha L_{i}^{1-\alpha}
$$
**注意**：厂商认为自己无法影响总量资本（实际上可以），因此存在外部性。

厂商的利润最大化条件为
$$
\frac{\partial Y_{i}(t)}{\partial K_{i}(t)}=\alpha B^{1-\alpha}K(t)^{1-\alpha} \left[ \frac{K_{i}(t)}{L_{i}} \right]^{\alpha-1}=R(t)
$$
**注意**：同质的厂商设定同样的 $\frac{K_{i}(t)}{L_{i}}$，相当于总体经济设定 $\frac{K(t)}{L}$

因此，边际私人产出(Marginal Private Product, MPP)为
$$
MPP_{K}=\left. \frac{\partial Y_{i}(t)}{\partial K_{i}(t)} \right|_{K_{i}=K}=\alpha B^{1-\alpha}K(t)^{1-\alpha} \left[ \frac{K(t)}{L} \right]^{\alpha-1}=\alpha(BL)^{1-\alpha}
$$
而根据总量生产函数可知边际社会产出(Marginal Social Product, MSP)为
$$
MSP_{K}=(BL)^{1-\alpha}
$$
因此，$MSP_{K}>MPP_{K}$，即私人投资不足，相应地增长率 $s\alpha B^{1-\alpha}L(0)^{1-\alpha}$ 较低。

根据市场出清条件、利润最大化条件
$$
r(t)=R(t)-\delta=f(k)-\delta
$$
我们假设没有折旧，因此均衡利率为 $r(t)=\alpha(BL)^{1-\alpha}$

如果进一步结合 [[02 宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] ，将利率代入欧拉方程可得
$$
\frac{\dot{c}(t)}{c(t)}=\frac{\alpha(BL)^{1-\alpha}-\rho}{\theta}=\bar{g}
$$
其中 $\bar{g}$ 就是 [[02 宏观经济学/AK Model\|AK Model]] 提到的消费、资本、产出的共同增长率。