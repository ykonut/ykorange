---
{"dg-publish":true,"permalink":"/宏观经济学/DSGE-不完全竞争/","created":"2024-10-12T10:25:04.000+08:00","updated":"2025-09-12T18:57:53.488+08:00"}
---

## 消费者

和 [[宏观经济学/DSGE Model\|DSGE Model]] 完全一致

## 厂商

家庭→price taker→中间品厂商→price searcher→最终品厂商→price taker→家庭

假设中间品厂商使用 [[微观经济学/数理经济学/Cobb-Douglas函数\|Cobb-Douglas函数]]生产，最终品厂商使用连续型 [[微观经济学/数理经济学/CES函数\|CES函数]] 生产

为了体现经济循环中各种价格之间的关系，不再将最终品价格 $P_{t}$ 标准化为 1.

最终品厂商利润最大化问题为
$$
\begin{split}
\max &\ \Pi=P_{t}Y_{t}-\int _{0}^1 P_{i,t}X_{i,t}\, di  \\
\text{s.t.} &\ Y_{t}=\left[\int _{0}^1 X_{i,t}^\rho \, di \right]^ \frac{1}{\rho}
\end{split}
$$
其中，$\sigma\equiv \frac{1}{1-\rho}$ 为替代弹性。

根据[[微观经济学/利润最大化\|利润最大化]]的一般解法
F.O.C.
$$
\frac{ \partial \Pi }{ \partial X_{i,t} } =P_{t} \frac{1}{\rho}\left[ \int _{0}^1 X_{i,t}^\rho\, di \right]^{\frac{1}{\rho}-1}\rho X_{i,t}^{\rho-1}-P_{i,t}=0
$$
which implies
$$
\left( \frac{X_{i,t}}{X_{j,t}} \right) ^{\rho-1}=\frac{P_{i,t}}{P_{j,t}}
$$
如果将其代回F.O.C.，由于有无穷个未知数构成的指数函数，分离它们并得出要素需求函数几乎不可能，因此考虑将生产函数作为桥梁“打包”所有未知数的信息。

根据生产函数有 $Y_{t}^\rho=\int _{0}^1 X_{i,t}^\rho \, di$，F.O.C.可以写为
$$
\begin{align}
P_{t}Y_{t}^{1-\rho}X_{i,t}^{\rho-1}-P_{i,t}&=0 \\
P_{t} \left(\frac{X_{i,t}}{Y_{t}}\right)^{\rho-1}&=P_{it}
\end{align}\implies X_{i,t}=\left( \frac{P_{i,t}}{P_{t}} \right)^{\frac{1}{\rho-1}}Y_{t}
$$
> 正是因为求导后没有破坏 $Y_{t}$ 的整体，才能顺利完成这一步，可见这就是 CES 生产函数的妙处之一。

现在得到了 $X_{i,t}(Y_{t},P_{t},P_{i,t})$ 而非条件要素需求函数 $X_{i,t}^c(Y_{t},\mathbf{P}_{t})$，因此还要消去 $P_{t}$

再次利用生产函数
$$
\begin{align}
Y_{t}&=\left[ \int_{0}^1 \left( \frac{P_{j,t}}{P_{t}} \right)^{\frac{\rho}{\rho-1}}Y_{t}^\rho \, dj \right]^ \frac{1}{\rho} \\
Y_{t}&=Y_{t} P_{t}^{\frac{1}{1-\rho}}\left[ \int_{0}^1 P_{j,t}^{\frac{\rho}{\rho-1}} \, dj \right]^{\frac{1}{\rho}}  \\
P_{t}&=\left[ \int_{0}^1 P_{j,t}^{\frac{\rho}{\rho-1}} \, dj  \right]^{\frac{\rho-1}{\rho}}
\end{align}
$$
代回原函数就得到了条件要素需求函数。

> 这里似乎走了一个弯路，虽然从利润最大化问题起手，但实际上求的是条件要素需求函数，不如直接考虑 [[微观经济学/数理经济学/CES函数\|CES函数]]成本最小化更为直接。

中间品厂商成本最小化问题为
$$
\begin{split}
\min &\ w_{t}L_{t}+r_{t}K_{t} \\
\text{s.t.} &\ A_{t}K_{t}^\alpha L_{t}^{1-\alpha}=X_{j,t}
\end{split}
$$
根据 [[微观经济学/数理经济学/Cobb-Douglas函数\|Cobb-Douglas函数]] 的性质可得
$$
\frac{r_{t}K_{t}}{w_tL_{t}}=\frac{\alpha}{1-\alpha}
$$
一般地，将上式代回F.O.C.就可以解得条件要素需求函数继而得到成本函数，但是我们只关心中间品厂商的边际成本，所以这里采用另一种路径，根据[[微观经济学/成本最小化\|成本最小化]]的结论
$$
MC=\frac{w}{MP_{L}}=\frac{r}{MP_{K}}
$$
因此
$$
\begin{align}
MC&=\frac{r_{t}}{A_{t}\alpha K_{t}^{\alpha-1}L_{t}^{1-\alpha}}=\frac{r_{t}}{\alpha\frac{X_{j,t}}{K_{t}}} \\
&=\frac{w_{t}}{A_{t}(1-\alpha) K_{t}^{\alpha}L_{t}^{-\alpha}}=\frac{w_{t}}{(1-\alpha)\frac{X_{j,t}}{L_{t}}}
\end{align}
$$
> 显然，这里也利用了 Cobb-Dauglas 生产函数求导不破坏产量信息的性质。

得到
$$
\begin{align}
K_{t}&=MC\alpha  \frac{X_{j,t}}{r_{t}} \\
L_{t}&=MC(1-\alpha) \frac{X_{j,t}}{w_{t}}
\end{align}
$$
从而得到边际成本函数 $MC(X_{j,t},K_{t},r_{t};L_{t},w_{t})$，但稍不同于一般的成本函数 $C(X_{j,t},r_{t},w_{t})$，因此再次利用生产函数消去生产要素的信息：
$$
\begin{align}
A_{t}\left( MC\alpha\frac{X_{j,t}}{r_{t}} \right)^\alpha \left( MC(1-\alpha)  \frac{X_{j,t}}{w_{t}} \right)^{1-\alpha}&=X_{j,t}  \\
A_{t}\left( \alpha\frac{1}{r_{t}} \right)^\alpha \left( (1-\alpha)  \frac{1}{w_{t}} \right)^{1-\alpha}&=\frac{1}{MC} \\
MC&=\frac{1}{A_{t}}\left( \frac{1}{\alpha} \right)^\alpha \left( \frac{1}{1-\alpha} \right)^{1-\alpha}r_{t}^\alpha w_{t}^{1-\alpha}
\end{align}
$$
> 这里的思路在于，条件要素需求函数的解析解十分复杂，而我们关心的仅仅是代回目标函数后得到的成本函数乃至边际成本函数，所以利用产量 $X_{j,t}$ 的信息作为桥梁直接求解边际成本，继而根据 $MR=MC$ 得出定价。


中间品厂商的利润最大化问题为
$$
\begin{split}
\max &\ P_{i,t}X_{i,t}-w_{t}L_{t}-r_{t}K_{t} \\
\end{split}
$$
其中（这是因为根据 [[微观经济学/数理经济学/CRS函数\|CRS函数]] 的性质 $MC=AC$）
$$
r_{t}K_{t}+w_{t}L_{t}=MCX_{j,t}
$$
代入中间品厂商面临的需求函数 $X_{j,t}=\left( \frac{P_{j,t}}{P_{t}} \right)^{\frac{1}{\rho-1}}Y_{t}=\left( \frac{P_{t}}{P_{j,t}} \right)^{\frac{1}{1-\rho}}Y_{t}$ 可得
$$
\max (P_{j,t}-MC)P_{t}^\frac{1}{1-\rho} P_{j,t}^ {\frac{1}{\rho-1}} Y_{t} 
$$

F.O.C.
$$
\begin{align}
P_{t}^\frac{1}{1-\rho} P_{j,t}^ {\frac{1}{\rho-1}} Y_{t} +\frac{1}{\rho-1}(P_{j,t}-MC)P_{t}^\frac{1}{1-\rho} P_{j,t}^ {\frac{1}{\rho-1}-1} Y_{t} &=0  \\
1+\frac{1}{\rho-1} \frac{P_{j,t}-MC}{P_{j,t}}&=0 \\
P_{j,t}&=\frac{MC}{\rho}
\end{align}
$$
因此，中间品厂商的定价是边际成本的加成（mark-up）

还可以直接通过垄断厂商的[[微观经济学/数理经济学/弹性#弹性定价法\|弹性#弹性定价法]]
$$
P_{i,t}\left( 1-\frac{1}{\varepsilon} \right)=MC
$$
其中，中间品厂商面临的需求函数 $X_{j,t}=\left( \frac{P_{j,t}}{P_{t}} \right)^{\frac{1}{\rho-1}}Y_{t}=\left( \frac{P_{t}}{P_{j,t}} \right)^{\frac{1}{1-\rho}}Y_{t}$ 的弹性 $\varepsilon$ 为
$$
\varepsilon=\frac{ \partial \log X_{j,t} }{ \partial \log P_{j,t} } =\frac{ \partial \frac{1}{\rho-1}[\log P_{j,t}-\log P_{t}]+\log Y_{t} }{ \partial \log P_{j,t} }=\frac{1}{1-\rho}
$$