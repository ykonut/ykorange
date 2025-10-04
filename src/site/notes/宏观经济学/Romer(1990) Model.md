---
{"dg-publish":true,"permalink":"/宏观经济学/Romer(1990) Model/","created":"2024-10-12T10:24:52.000+08:00","updated":"2024-10-12T10:24:52.000+08:00"}
---


该模型是内生技术变迁的最简模型，通过 R&D 扩展生产投入的种类刻画创新。
- 创意和技术是非竞争性的
- 规模报酬递增
- R&D 具有固定成本
模型包含三个部门：
- 研究部门(research sector)使用人力资本和知识存量生产新知识；
- 中间产品部门(intermediate-goods sector)使用知识生产中间产品；
- 最终产品部门(final-goods sector)使用劳动力、人力资本和中间产品生产最终产品

## 最终产品部门
最终产品的生产函数为
$$
Y=H_{Y}^\alpha L^\beta \int_{0}^{A} x(i)^{1-\alpha-\beta} \, \mathrm{d}i 
$$
其中：
- $H_Y$ 为生产最终产品的人力资本，假设供给量是固定的
- $L$ 为劳动，假设供给量是固定的
- $A$ 为中间产品的数量
- $x(i)$ 为第 $i$ 种中间产品

资本的动态方程为
$$
\dot{K}(t)=Y(t)-C(t)
$$
这里相当于假设资本没有折旧，没有被消费的产出 1:1 可以转化为资本。

最终产品部门为竞争性，利润最大化问题为
$$
\max_{x(i)} H_{Y}^\alpha L^\beta \int_{0}^{A} x(i)^{1-\alpha-\beta} \, \mathrm{d}i -w_{H}H_{Y}^\alpha-w_{L}L-\int_{0}^{A} p(i)x(i)  \, \mathrm{d}x 
$$
其中：
-  $w_H$ 是人力资本的租金
- $w_{L}$ 是劳动的工资
- $p(i)$ 是第 $i$ 种投入品的价格

最优租金和工资为
$$
\begin{align}
w_{H} & =\alpha H_{Y}^{\alpha-1}L^\beta \int_{0}^{A} x(i)^{1-\alpha-\beta} \, \mathrm{d}i \\
w_{L} & =\beta H_{Y}^\alpha L^{\beta-1} \int_{0}^{A} x(i)^{1-\alpha-\beta} \, \mathrm{d}i
\end{align}
$$
我们唯一需要关心的是对中间产品的反需求函数：
$$
(1-\alpha-\beta)H_{Y}^\alpha L^\beta x(i)^{-\alpha-\beta}=p(i)
$$

显然，其需求价格弹性为 $\varepsilon=\frac{\mathrm{d} \ln x(i)}{\mathrm{d} p(i)} =\frac{1}{-\alpha-\beta}$

## 中间产品部门
中间产品的生产函数为
$$
x(i)=K(i)
$$
中间产品部门为垄断性，利润最大化问题为
$$
\begin{align}
\max_{x(i)} &\ \pi(i)=p(i)x(i)-rK_{i} \\
\text{s.t.} &\ x(i)=K(i)
\end{align}
$$
根据[[微观经济学/垄断\|垄断]]最优化条件 $P\left( 1+\frac{1}{\varepsilon} \right)=MC$ 可得
$$
r=p(i)(1-\alpha-\beta)
$$
垄断租金为
$$
\pi(i)=(p_{i}-r)x_{i}=(\alpha+\beta)p(i)x(i)
$$
> [!NOTE]
> 这里构造的利润函数只包含可变要素 $K_{i}$ ，并没有包含固定要素——知识 $A^i$，因为固定要素的报酬将全部转移给知识部门，因此这里所谓的利润实际上是租金。若将租金纳入成本则中间产品部门真正的利润仍然是零。

## 研发部门

知识的生产函数为
$$
\dot{A}=\delta H_{A}A
$$
其中：
- $\delta$ 为生产率参数
- $H_{A}$ 为生产知识的人力资本，假设供给量是固定的
- $A$ 为知识存量
> 假设研究厂商 $j$ 拥有 $H_{A}^j$ 的人力资本和 $A^j$ 的知识存量能以 $\delta$ 的生产率产出第 $j$ 种知识；进一步假设知识存量是非竞争性的，对 $j\in(0,A)$ 加总就得到知识的生产函数。 

研究部门的利润最大化问题为
$$
\begin{align}
\max_{H_{A}} &\ P_{A}\dot{A}-w_{H}H_{A} \\
\text{s.t.} &\ \dot{A}=\delta H_{A}A
\end{align}
\implies
P_{A}\delta A=w_{H}
$$
其中
-  $P_{A}$ 是新知识的售价
- $w_H$ 是人力资本的租金

> [!NOTE]
> 这里的关键之处在于，作为知识的完全垄断者，生产 $A^j$ 的研究厂商能吃光中间产品厂商 $i$ 的垄断租金，即 $P_{A}$ 相当于中间产品部门的全部垄断资金。实际上完全可以将中间产品部门和研究部门看作同一个部门，从而消去这种内部交易的价格。这里分开处理只是为了使得机制更加清晰。

根据售价=垄断租金可得
$$
P_{A}(t)=\int_{t}^{\infty}  \exp\left[ -\int_{t}^{\tau} r(s) \, \mathrm{d}s  \right] \pi(\tau)\, \mathrm{d}\tau
$$
**注意**：中间产品厂商是同质的，因此不再需要以 $(i)$ 编码，这里的 $(\tau)$ 是时间编码。
> [!NOTE]
> 根据 Grossman&Helpman (1989c)，上式可以化为
> $$
> \pi(t)=r(t)P_{A}(t)
> $$
> 即 $t$ 期中间产品部门的利润应等于期初花费 $P_{A}$ 的利息成本。

## 均衡
家庭部门的动态最优化问题和 [[宏观经济学/Ramsey-Cass-Koopmans Model\|Ramsey-Cass-Koopmans Model]] 相似
$$
\begin{align}
\max_{C(t)} &\ \int_{0}^{\infty} \frac{C(t)^{1-\sigma}-1}{1-\sigma} e^{-\rho t} \, \mathrm{d}t \\
\text{s.t.} &\ \dot{K}(t)=r(t)K(t)+w_{L}L+w_{H}H-C(t) \\
&\ \lim_{t\to \infty}K(t)\exp\left[ -\int_{0}^{t} r(s) \, \mathrm{d}s  \right]\geq 0
\end{align}
$$
这个模型解的变式只和 $\frac{\partial H}{\partial K}$ 有关，因此欧拉方程还是经典形式
$$
\frac{\dot{C}(t)}{C(t)}=\frac{r(t)-\rho}{\sigma}
$$
这里和 [[宏观经济学/AK Model\|AK Model]] 一样欧拉方程给出的实际上是消费、资本、技术和产出的共同增长率，其中
$$
\begin{align}
r(t)=\frac{\pi(t)}{P_{A}}=\frac{(\alpha+\beta)p(i)x(i)}{w_{H}/\delta A}
\end{align}
$$
中间产品厂商是同质的，因此最终产品厂商的最优条件可以写为
$$
\begin{align}
p(i) & =(1-\alpha-\beta)H_{Y}^\alpha L^\beta \bar{x}^{-\alpha-\beta} \\
w_{H} & =\alpha H_{Y}^{\alpha-1}L^\beta A \bar{x}^{1-\alpha-\beta}
\end{align}
$$
从而
$$
\begin{align}
r(t) & =(\alpha+\beta)\bar{x}\delta A \frac{(1-\alpha-\beta)H_{Y}}{\alpha A\bar{x}} \\
 & =\frac{(\alpha+\beta)(1-\alpha-\beta)}{\alpha} \delta H_{Y} \\
 & =\frac{1}{\Lambda} \delta(H-H_{A}) \\
 & =\frac{\delta H-\frac{\dot{A}}{A}}{\Lambda}
\end{align}
$$
其中
-  $\Lambda\equiv \frac{\alpha}{(\alpha+\beta)(1-\alpha-\beta)}$
- $\frac{\dot{A}}{A}=g$

因此
$$
g=\frac{\delta H-\Lambda\rho}{\Lambda\sigma+1}
$$


---
## 基本假设

代表性家庭的偏好为
$$
U=\int_{0}^{\infty} e^{-\rho t} \frac{C^{1-\theta}-1}{1-\theta}\, \mathrm{d}t
$$
**注意**：上式蕴含 $L(t)=L$；从 [[宏观经济学/AK Model\|AK Model]] 可知人口增长率 $n$ 并不重要，这里完全舍弃了

最终产品的总量生产函数为
$$
Y(t)=\frac{1}{1-\beta}\left[ \int_{0}^{N(t)} x(v,t)^{1-\beta} \, \mathrm{d}v  \right]L^\beta
$$
其中：
-  $N(t)$ 表示 $t$ 时刻投入品的种类；
- $x(v,t)$ 表示 $t$ 时刻的第 $v$ 种投入品
see also [[微观经济学/产业组织理论/Dixit-Stiglitz Model\|Dixit-Stiglitz Model]]

经济资源约束为
$$
C(t)+X(t)+Z(t)\leq Y(t)
$$
其中：
- $X(t)$ 为 $t$ 时刻的投入品投资
- $Z(t)$ 为 $t$ 时刻的 R&D 支出

创新可能性边界为
$$
\dot{N}(t)=\eta Z(t)
$$
其中， $\eta>0$，初值条件为 $N(0)>0$
因此，任何厂商在 $t$ 时刻都可以花费1单位产出获得 $\eta$ 单位新投入品的专利。

假设最终产品厂商需要以 $p_{x}(v,t)$ 的价格获取投入品 $x(v,t)$，利润最大化问题为
$$
\max_{\{ x(v,t) \}_{v\in[0,N(t)]}}  \frac{1}{1-\beta}\left[ \int_{0}^{N(t)} x(v,t)^{1-\beta} \, \mathrm{d}v  \right]L^\beta-\int_{0}^{N(t)} p_{x}(v,t)\cdot x(v,t) \mathrm{d}v-w(t)L
$$
解得投入品需求函数为
$$
x(v,t)=p_{x}(v,t)^{-\frac{1}{\beta}}L
$$
**注意**：投入品需求仅和其价格相关，与 $w(t)$ 无关（没有交叉价格效应）

假设投入品厂商以不变的边际成本 $\psi$ 生产投入品 $x(v,t)$，利润最大化问题为
$$
\max V(v,t)=\int_{0}^{\infty} \exp\left[ -\int_{t}^{s} r(s') \, \mathrm{d}s'  \right]\pi(v,s) \, \mathrm{d}s
$$
其中
$$
\pi(v,t)\equiv p_{x}x(v,t)-\psi x(v,t)
$$
上述目标函数可以写为 Hamilton-Jacobi-Bellman 递归形式
$$
r(t)V(v,t)-\dot{V}(v,t)=\pi(v,t)
$$