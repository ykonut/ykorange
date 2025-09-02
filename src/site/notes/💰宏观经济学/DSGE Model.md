---
{"dg-publish":true,"permalink":"/💰宏观经济学/DSGE Model/","created":"2024-10-12T10:25:04.000+08:00","updated":"2025-09-02T11:09:28.000+08:00"}
---

## 消费者

效用最大化问题为
$$
\begin{split}
\max &\ \sum_{t=0}^\infty \beta^t U(C_{t},O_{t}) \\
\text{s.t.} &\ U(C_{t},O_{t})=\gamma \ln C_{t}+\ln(1-\gamma)O_{t} \\
&\ O_{t}+L_{t}\equiv 1\\
&\ C_{t}+I_{t}=w_{t}L_{t}+r_{t}K_{t}\\
&\ I_{t}=K_{t+1}-(1-\delta)K_{t}
\end{split}
$$
等价于
$$
\begin{split}
\max &\ \sum_{t=0}^\infty \beta^t[\gamma \ln C_{t}+(1-\gamma)\ln(1-L_{t})] \\
\text{s.t.} &\ C_{t}+K_{t+1}=w_{t}L_{t}+(1+r_{t}-\delta)K_{t}
\end{split}
$$
Lagrangian is
$$
\begin{align*}
\mathcal{L}=& \sum_{t=0}^\infty \beta^t\{[\gamma \ln C_{t}+(1-\gamma)\ln(1-L_{t})] \\
&{}+\lambda_{t}[w_{t}L_{t}+(1+r_{t}-\delta)K_{t}-C_{t}-K_{t+1}] \} 
\end{align*}
$$
F.O.C
$$
\begin{align*}
\frac{\partial \mathcal{L}}{\partial C_{t}}&=\beta^t\left[ \frac{\gamma}{C_{t}}-\lambda_{t} \right]=0 \tag{1}\\
\frac{\partial \mathcal{L}}{\partial L_{t}}&=\beta^t\left[ -\frac{1-\gamma}{1-L_{t}}+\lambda_{t}w_{t} \right]=0 \tag{2}\\
\frac{\partial \mathcal{L}}{\partial K_{t}}&=\beta^t\lambda_{t}(1+r_{t}-\delta)+\beta^{t-1}\lambda_{{t-1}}(-1)=0 \tag{3}
\end{align*}
$$
由 $(1)(2)$ 可得
$$
\frac{\frac{1-\gamma}{1-L_{t}}}{\frac{\gamma}{C_{t}}}=w_{t}\implies \frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}=w_{t}
$$ which in fact is in [[⚖️微观经济学/效用最大化\|效用最大化]]
$$
\frac{U_{O}}{U_{C}}=\frac{P_{O}}{P_{C}}=\frac{w_{t}}{1}
$$
由 $(1)$ 得到欧拉方程再利用 $(3)$ 消去 $\lambda$ 可得
$$
\frac{C_{t}}{C_{t-1}}=\beta(1+r_{t}-\delta)
$$
which exactly in [[⚖️微观经济学/跨期效用最大化\|跨期效用最大化]]
$$
\frac{U_{C,t-1}}{U_{C,t}}=\beta(1+r_{t}-\delta)
$$
### 试试 Bellman Equation
$$
\begin{split}
\max &\ E_{0}\sum_{t=0}^\infty \beta^t[\gamma \ln C_{t}+(1-\gamma)\ln(1-L_{t})] \\
\text{s.t.} &\ C_{t}+K_{t+1}=w_{t}L_{t}+(1+r_{t}-\delta)K_{t}
\end{split}
$$
Bellman Equation 为
$$
\begin{align}
V(K_{t})=&\max_{K_{t+1},L_{t}} \gamma\ln [w_{t}L_{t}+(1+r_{t}-\delta)K_{t}-K_{t+1}] \\
&+(1-\gamma)\ln(1-L_{t})+\beta E_{t}V(K_{t+1})
\end{align}
$$
F.O.C.
$$
\begin{align}
\frac{\partial V_{t}}{\partial K_{t+1}}&=-\frac{\gamma}{w_{t}L_{t}+(1+r_{t}+\delta)K_{t}-K_{t+1}} +\beta E_{t}\frac{\partial V_{t+1}}{\partial K_{t+1}} =0 \\
\frac{\partial V_{t}}{\partial L_{t}}&= \frac{\gamma w_{t}}{w_{t}L_{t}+(1+r_{t}+\delta)K_{t}-K_{t+1}}+\frac{1-\gamma}{1-L_{t}}=0
\end{align}
$$
根据包络定理
$$
\begin{align}
\frac{\partial V_{t}}{\partial K_{t}}&=\frac{\gamma(1+r_{t}-\delta)}{w_{t}L_{t}+(1+r_{t}+\delta)K_{t}-K_{t+1}} \implies \frac{\partial V_{t+1}}{\partial K_{t+1}} \\
\end{align}
$$
F.O.C.写为
$$
\frac{C_{t+1}}{C_{t}}=\beta (1+r_{t+1}-\delta)
$$
以及
$$
\frac{\frac{1-\gamma}{1-L_{t}}}{\frac{\gamma}{C_{t}}}=w_{t}\implies \frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}=w_{t}
$$
和拉格朗日乘数法得到的结果完全一致。


## 厂商

由于消费 $C_{t}$ 被看作唯一商品，相当于假设 $P_{t}\equiv 1$

利润最大化问题为
$$
\begin{split}
\max &\ E_{0}\sum_{t=0}^\infty \left( \frac{1}{1+r_{t}} \right)
{ #t}
 \Pi_{t} \\
\text{s.t.} &\ \Pi_{t}=Y_{t}-w_{t}L_{t}-r_{t}K_{t} \\
&\ Y_{t}=A_{t}K_{t}^\alpha L_{t}^{1-\alpha}
\end{split}
$$
假设居民是生产要素的所有者，因此 $r_{t}$ 对厂商而言是外生变量，问题转化为
$$
\begin{split}
\max &\ \Pi_{t}=Y_{t}-w_{t}L_{t}-r_{t}K_{t} \\
\text{s.t.} &\ Y_{t}=A_{t}K_{t}^\alpha L_{t}^{1-\alpha}
\end{split}
$$
F.O.C
$$
\begin{align*}
\frac{\partial \Pi_{t}}{\partial K_{t}} &=\alpha A_{t}K_{t}^{\alpha-1}L_{t}^{1-\alpha }-r_{t}=0 \\
\frac{\partial \Pi_{t}}{\partial L_{t}} &=(1-\alpha)A_{t}K_{t}^\alpha L_{t}^{-\alpha}-w_{t}=0
\end{align*}
$$
which implies（[[⚖️微观经济学/数理经济学/Cobb-Douglas函数#利润最大化\|Cobb-Douglas函数#利润最大化]]的性质）
$$
\frac{r_{t}K_{t}}{w_{t}L_{t}}=\frac{\alpha}{1-\alpha}
$$
and（[[⚖️微观经济学/数理经济学/CRS函数\|CRS函数]]的性质）
$$
\begin{align*}
r_{t}K_{t}&=\alpha Y_{t} \\
w_{t}L_{t}&=(1-\alpha)Y_{t}
\end{align*}
$$

## 市场经济一般均衡模型

市场经济由七个变量序列刻画：$\{C_{t},I_{t},K_{t},L_{t},r_{t},w_{t},Y_{t}\}_{t=0}^\infty$

市场经济一般均衡为：
$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}&=w_{t} \tag{M1'}\\
\frac{C_{t}}{C_{t-1}}&=\beta(1+r_{t}-\delta) \tag{M2'}\\
\frac{r_{t}K_{t}}{w_{t}L_{t}}&=\frac{\alpha}{1-\alpha} \tag{M3'} \\
Y_{t}&=w_{t}L_{t}+r_{t}K_{t} \tag{M4'}\\
Y_{t}&=C_{t}+I_{t} \tag{M5'}\\
Y_{t}&=A_{t}K_{t}^\alpha L_{t}^{1-\alpha} \tag{M6'}\\
I_{t}&=K_{t+1}-(1-\delta)K_{t} \tag{M7'}
\end{align*}
$$
分别是居民均衡 $(M1')(M2')$，厂商均衡 $(M3')$，国民经济恒等式 $(M4')(M5')(M6')$，和资本积累方程 $(M7')$

为了后期代换便捷，可以显示表达 $r_{t},w_{t}$ 两个价格，由 $(M3')(M4')$ 可得 $(M 3)(M 4)$，写为：
$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}&=w_{t} \tag{M1}\\
\frac{C_{t}}{C_{t-1}}&=\beta(1+r_{t}-\delta) \tag{M2}\\
r_{t}&=\alpha A_{t}K_{t}^{\alpha-1}L_{t}^{1-\alpha }=\frac{\alpha Y_{t}}{K_{t}} \tag{M3} \\
w_{t}&=(1-\alpha)A_{t}K_{t}^\alpha L_{t}^{-\alpha}=\frac{(1-\alpha)Y_{t}}{L_{t}} \tag{M4}\\
Y_{t}&=C_{t}+I_{t} \tag{M5}\\
Y_{t}&=A_{t}K_{t}^\alpha L_{t}^{1-\alpha} \tag{M6}\\
I_{t}&=K_{t+1}-(1-\delta)K_{t} \tag{M7}
\end{align*}
$$

## 计划经济一般均衡模型 

将居民效用最大化和厂商利润最大化问题统一，合并为善良独裁者对居民效用最大化的决策问题。换言之，略去厂商利润最大化，将居民效用最大化的“支出=收入” 条件变为“支出=产出”条件，市场分配变为计划分配，价格机制消失。

The problem is
$$
\begin{split}
\max &\ E_{0}\sum_{t=0}^\infty \beta^t U(C_{t},O_{t}) \\
\text{s.t.} &\ U(C_{t},O_{t})=\gamma \log C_{t}+(1-\gamma)O_{t} \\
&\ O_{t}+L_{t}\equiv 1\\
&\ C_{t}+I_{t}=A_{t}K_{t}^\alpha L_{t}^{1-\alpha}\\
&\ I_{t}=K_{t+1}-(1-\delta)K_{t}
\end{split}
$$
计划经济由五个变量序列刻画：$\{C_{t},I_{t},K_{t},L_{t},Y_{t}\}_{t=0}^\infty$

计划经济一般均衡为：
$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}&=(1-\alpha)A_{t}K_{t}^\alpha L_{t}^{-\alpha} \tag{P1}\\
\frac{C_{t}}{C_{t-1}}&=\beta(1+\alpha A_{t}K_{t}^{\alpha-1}L_{t}^{1-\alpha }-\delta) \tag{P2}\\
Y_{t}&=C_{t}+I_{t} \tag{P3}\\
Y_{t}&=A_{t}K_{t}^\alpha L_{t}^{1-\alpha} \tag{P4}\\
I_{t}&=K_{t+1}-(1-\delta)K_{t} \tag{P5}
\end{align*}
$$
## 市场经济均衡的稳态

$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{\bar{C}}{1-\bar{L}}&=\bar{w} \tag{sM1}\\
1&=\beta(1+\bar{r}-\delta) \tag{sM2}\\
\bar{r}&=\alpha \bar{A}\bar{K}^{\alpha-1}\bar{L}^{1-\alpha }=\frac{\alpha \bar{Y}}{\bar{K}} \tag{sM3} \\
\bar{w}&=(1-\alpha)\bar{A}\bar{K}^\alpha \bar{L}^{-\alpha}=\frac{(1-\alpha)\bar{Y}}{\bar{L}} \tag{sM4}\\
\bar{Y}&=\bar{C}+\bar{I} \tag{sM5}\\
\bar{Y}&=\bar{A}\bar{K}^\alpha \bar{L}^{1-\alpha} \tag{sM6}\\
\bar{I}&=\bar{K}-(1-\delta)\bar{K}\implies \bar{I}=\delta \bar{K} \tag{sM7}
\end{align*}
$$
## 中央计划均衡的稳态

$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{\bar{C}}{1-\bar{L}}&=(1-\alpha)\bar{A}\bar{K}^\alpha \bar{L}^{-\alpha} \tag{sP1}\\
1&=\beta(1+\alpha \bar{A}\bar{K}^{\alpha-1}\bar{L}^{1-\alpha }-\delta) \tag{sP2}\\
\bar{Y}&=\bar{C}+\bar{I} \tag{sP3}\\
\bar{Y}&=\bar{A}\bar{K}^\alpha \bar{L}^{1-\alpha} \tag{sP4}\\
\bar{I}&=\delta \bar{K} \tag{sP5}
\end{align*}
$$
## 求解稳态

在 $sM$ 中消去价格得到 $sP$，进一步消去 $(sP 4)(sP 5)$ 得到
$$
\begin{align*}
\frac{1-\gamma}{\gamma}\frac{\bar{C}}{1-\bar{L}}&=(1-\alpha) \frac{\bar{Y}}{\bar{L}}\tag{1}\\
1&=\beta\left( 1+\alpha \frac{\bar{Y}}{\bar{K}}-\delta \right)\tag{2}\\
\bar{Y}&=\bar{C}+\delta \bar{K}\tag{3}
\end{align*}
$$
由 $(2)$ 可得
$$
\bar{K}=\frac{\alpha\beta}{1+\beta\delta-\beta}\bar{Y}\tag{4}
$$
由 $(3)(4)$ 可得
$$
\bar{C}=\frac{1+(1-\alpha)\beta\delta-\beta}{1+\beta\delta-\beta}\bar{Y}\tag{5}
$$
由 $(1)(5)$ 可得
$$
\bar{L}=\frac{\gamma(1-\alpha)(1+\beta\delta-\beta)}{(1-\gamma)[1+(1-\alpha)\beta\delta-\beta]+\gamma(1-\alpha)(1+\beta\delta-\beta)}\bar{Y}\tag{6}
$$
将 $(4)(6)$ 代回 $(sM 3)(sM 4)$ 可得
$$
\begin{align*}
\bar{r}&=\frac{1}{\beta}+\delta-1\\
\bar{w}&=\frac{(1-\gamma)[1+(1-\alpha)\beta\delta-\beta]}{\gamma(1+\beta\delta-\beta)}+(1-\alpha)
\end{align*}
$$
还有最复杂的 $\bar{Y}$ 以及最容易的 $\bar{I}$
## 对数线性化

定义：$\hat{u}_{t}\equiv\ln u_{t}-\ln \bar{u}\implies u_{t}=\bar{u}e^{\hat{u}_{t}}\approx \bar{u}(1+\hat{u}_{t})$

假设：
-  $u_{t}z_{t}\approx 0$
- $u_{t}^a\approx \bar{u}^a(1+\hat{u}_{t})^a\approx \bar{u}^a(1+a\hat{u}_{t})$

此外假设
$$
\ln A_{t}=(1-\rho_{A})\ln \bar{A}+\rho_{A}\ln A_{t-1}+\varepsilon_{t}^A\ ,\varepsilon_{t}^A\sim N(0,\sigma_{A}^{2})
$$
using $(M 1)$
$$

$$

using $(M 5)$
$$
\begin{align*}
\bar{Y}(1+\hat{y}_{t})&=\bar{C}(1+\hat{c}_{t})+\bar{I}(1+\hat{i}_{t})\\
\hat{y}_{t}&=\frac{\bar{C}}{\bar{Y}}\hat{c}_{t}+\frac{\delta \bar{K}}{\bar{Y}}\hat{i}_{t}\\
\hat{y}_{t}&=\frac{1+(1-\alpha)\beta\delta-\beta}{1+\beta\delta-\beta}\hat{c}_{t}+\frac{\alpha\beta\delta}{1+\beta\delta-\beta}\hat{i}_{t}\\
(1+\beta\delta-\beta)\hat{y}_{t}&=[1+(1-\alpha)\beta\delta-\beta]\hat{c}_{t}+\alpha\beta\delta \hat{i}_{t}
\end{align*}
$$
using $(M6)$
$$
\begin{align*}
\bar{Y}(1+\hat{y}_{t})&=\bar{A}\bar{K}^\alpha \bar{L}^{1-\alpha}(1+\hat{a}_{t}+\alpha \hat{k}_{t}+(1-\alpha)\hat{l}_{t})\\
\hat{y}_{t}&=1+\hat{a}_{t}+\alpha \hat{k}_{t}+(1-\alpha)\hat{l}_{t}
\end{align*}
$$

