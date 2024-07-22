---
{"dg-publish":true,"permalink":"/02 宏观经济学/Real-Business-Cycle (RBC) Model/","created":"2024-06-23T22:43:43.000+08:00","updated":"2024-06-23T22:43:43.000+08:00"}
---

## 消费者

### 偏好集
效用函数为
$$
u(c_{t},1-h_{t})
$$
其中 $c_{t}$ 表示消费，$h_{t}$ 表示劳动

劳动有两种调整的边际：
1. 内边际（Intensive margin）：选择劳动时间，即劳动是可分的
2. 外边际（Extensive margin）：选择是否工作，即劳动是不可分的

这里考虑劳动不可分的情形。假设企业与同质的劳动者签订同样的劳动合同，使得劳动者以 $\alpha_{t}$ 的概率选择 $h_{0}$ 的劳动水平，以 $1-\alpha_{t}$ 的概率选择不工作。无论劳动者事后选择工作与否都会得到工资，即完全失业保险制度。

定义 $h_{t}\equiv\alpha_{t}h_{0}+(1-\alpha)\cdot0$ ，此时效用函数变为
$$
\begin{align}
u(c_{t},1-h_{t})&=[\gamma \ln c_{t}+(1-\gamma)\ln (1-h_{0})]\alpha_{t}+[\gamma \ln c_{t}+(1-\gamma)\ln (1-0)](1-\alpha_{t}) \\
&=\gamma \ln c_{t}+(1-\gamma)\alpha_{t}\ln(1-h_{0}) \\
&=\gamma \ln c_{t}+(1-\gamma) \frac{\ln(1-h_{0})}{h_{0}}h_{t}
\end{align}
$$
为方便起见，单调变换后得到最终的效用函数为
$$
u(c_{t},1-h_{t})\equiv \ln c_{t}+B h_{t}
$$
其中， $B=\frac{1-\gamma}{\gamma} \frac{\ln(1-h_{0})}{h_{0}}$
### 选择集

消费者的一般预算约束为
$$
c_{t}+\underbrace{ [k_{t+1}-(1-\delta)k_{t}] }_{ i_{t} }=w_{t}h_{t}+r_{t}k_{t}
$$
此外考虑货币先行约束（Cash-in-Advance Constraint, CIA），即使用名义货币消费
$$
p_{t}c_{t}\leq m_{t-1}+T
$$
其中 $p_{t}$ 是价格水平，$m_{t-1}$ 是上期留存至当期的货币，$T$ 是政府转移支付的货币。

假设
$$
T\equiv M_{t}-M_{t-1}=\left( \frac{M_{t}}{M_{t-1}}-1 \right)M_{t-1}=(g_{t}-1)M_{t-1}
$$
其中 $M_{t}$ 是人均货币存量（实际上也是货币总量），$g_{t}\equiv \frac{M_{t}}{M_{t-1}}$ 是货币增长率。

此时，消费者一般预算约束改写为
$$
p_{t}\{c_{t}+[k_{t+1}-(1-\delta)k_{t}]\}+m_{t}=p_{t}(w_{t}h_{t}+r_{t}k_{t})+m_{t-1}+(g_{t}-1)M_{t-1}
$$

可以考虑两种货币供应法则：
- $g_{t}=\bar{g}$，固定货币增长率
- $g_{t}$ 服从某个随机过程

一般地，当 $\bar{g}\neq 1$ 时，一般找不到 $p_{t},m_{t},M_{t}$ 的稳态值，因此需要标准化相关变量。

定义 $\hat{p}_{t}=\frac{p_{t}}{M_{t}},\hat{m}_{t}=\frac{m_{t}}{M_{t}}$，从而将预算约束改写为
$$
\begin{align}
\hat{p}_{t}\{c_{t}+[k_{t+1}-(1-\delta)k_{t}]\}+\hat{m}_{t}&=\hat{p}_{t}(w_{t}h_{t}+r_{t}k_{t})+\frac{m_{t-1}+(g_{t}-1)M_{t-1}}{M_{t}} \\
\hat{p}_{t}\{c_{t}+[k_{t+1}-(1-\delta)k_{t}]\}+\hat{m}_{t}&=\hat{p}_{t}(w_{t}h_{t}+r_{t}k_{t})+\frac{\hat{m}_{t-1}+(g_{t}-1)}{g_{t}} \\
c_{t}+[k_{t+1}-(1-\delta)k_{t}]+\frac{\hat{m}_{t}}{\hat{p}_{t}}&=w_{t}h_{t}+r_{t}k_{t}+\frac{\hat{m}_{t-1}+(g_{t}-1)}{g_{t}\hat{p}_{t}}
\end{align}
$$
CIA 约束改写为
$$
\begin{align}
\hat{p}_{t}c_{t}&=\frac{m_{t-1}+(g_{t}-1)M_{t-1}}{M_{t}} \\
c_{t}&=\frac{\hat{m}_{t-1}+(g_{t}-1)}{g_{t}\hat{p}_{t}}
\end{align}
$$
### 最优化

消费者最优化问题为
$$
\begin{split}
\max &\ E_{0}\sum_{0}^\infty \beta^t(\ln c_{t}+Bh_{t}) \\
\text{s.t.} &\ k_{t+1}-(1-\delta)k_{t}+\frac{\hat{m}_{t}}{\hat{p}_{t}}=w_{t}h_{t}+r_{t}k_{t} \\
&\ c_{t}=\frac{\hat{m}_{t-1}+(g_{t}-1)}{g_{t}\hat{p}_{t}}
\end{split}
$$
> 注意：CIA 约束将预算约束的货币部分消去了

Lagrangian is
$$
\begin{align*}
\mathcal{L}=&E_{0}  \sum_{t=0}^\infty \beta^t\{[\ln c_{t}+Bh_{t}] \\
&{}+\chi_{t}^1[w_{t}h_{t}+(1+r_{t}-\delta)k_{t}-\frac{\hat{m}_{t}}{\hat{p}_{t}}-k_{t+1}] \\
&{}+\chi_{t}^2[\frac{\hat{m}_{t-1}+(g_{t}-1)}{g_{t}\hat{p}_{t}}-c_{t}]\} 
\end{align*}
$$
F.O.C.

> 注意凡是要递推到 $t+1$ 的部分都要 conditional on $t$，这是因为包含随机变量 $g_{t}$

$$
\begin{align}
\frac{ \partial \mathcal{L} }{ \partial c_{t} }&=\beta^t\left[ \frac{1}{c_{t}}-\chi_{t}^2 \right]=0 \tag{1}\\
\frac{ \partial \mathcal{L} }{ \partial h_{t} }&=\beta^t[B+\chi_{t}^1w_{t}]=0 \tag{2}\\
\frac{ \partial \mathcal{L} }{ \partial k_{t+1} }&=-\beta^t\chi_{t}^1+\beta^{t+1}E_{t}[\chi_{t+1}^1(1+r_{t+1}+\delta)]=0 \tag{3} \\
\frac{ \partial \mathcal{L} }{ \partial \hat{m}_{t} }&=-\beta^t\frac{\chi_{t}^1}{\hat{p}_{t}}+\beta^{t+1}E_{t}\left[ \frac{\chi_{t+1}^2}{g_{t+1}\hat{p}_{t+1}} \right]=0 \tag{4}
\end{align}
$$
解得
$$
\begin{align}
\chi_{t}^1&=-\frac{B}{w_{t}} \tag{1}\\
\chi_{t}^2&=\frac{1}{c_{t}} \tag{2}\\
\chi_{t}^1&=\beta E_{t}[\chi_{t+1}^1(1+r_{t+1}+\delta)] \tag{3}\\
\frac{\chi_{t}^1}{\hat{p}_{t}}&=\beta E_{t}\left[ \frac{\chi_{t+1}^2}{g_{t+1}\hat{p}_{t+1}} \right] \tag{4}
\end{align}
$$
也即
$$
\begin{align}
\frac{w_{t+1}}{w_{t}}&=\beta E_{t}(1+r_{t+1}+\delta) \\
\frac{c_{t+1}}{w_{t}}&=-\frac{\beta}{B}E_{t}\left[ \frac{\hat{p}_{t}} {g_{t+1}\hat{p}_{t+1}} \right] 
\end{align}
$$
## 厂商

$$
\begin{split}
\max &\ \Pi_{t}=Y_{t}-w_{t}H_{t}-r_{t}K_{t} \\
\text{s.t.} &\ Y_{t}=\lambda_{t}K_{t}^\theta L_{t}^{1-\theta}
\end{split}
$$
F.O.C.
$$
\begin{align}
r_{t}&=\theta \lambda_{t}K_{t}^{\theta-1}H_{t}^{1-\theta}=\theta\frac{ Y_{t}}{K_{t}} \\
w_{t}&=(1-\theta)\lambda_{t} K_{t}^\theta H_{t}^{-\theta}=(1-\theta) \frac{Y_{t}}{H_{t}}
\end{align}
$$
## 一般均衡

对于代表性劳动者而言有
$$
\begin{align}
K_t&=\int _{0}^1 k_{t} \, di=k_{t} \\
H_{t}&=\int _{0}^1 h_{t} \, di=h_{t}  \\
C_{t}&=\int _{0}^1 c_{t} \, di=c_{t}  \\
M_{t}&=\int _{0}^1 m_{t} \, di=m_{t}
\end{align}
$$
最后一项意味着 $\hat{M}_{t}=\hat{m}_{t}=\frac{M_{t}}{M_{t}}=1$

一般均衡模型为
$$
\begin{align}
k_{t+1}+\frac{\hat{m}_{t}}{\hat{p}_{t}}&=w_{t}h_{t}+(1+r_{t}-\delta)k_{t} \\
c_{t}&=\frac{\hat{m}_{t-1}+(g_{t}-1)}{g_{t}\hat{p}_{t}}=\frac{1}{\hat{p}_{t}} \\
\frac{w_{t+1}}{w_{t}}&=\beta E_{t}(1+r_{t+1}+\delta) \\
\frac{c_{t+1}}{w_{t}}&=-\frac{\beta}{B}E_{t}\left[ \frac{\hat{p}_{t}} {g_{t+1}\hat{p}_{t+1}} \right] \\
r_{t}&=\theta \lambda_{t} \left( \frac{k_{t}}{h_{t}} \right)^{\theta-1} \\
w_{t}&=(1-\theta) \lambda_{t} \left( \frac{k_{t}}{h_{t}} \right)^\theta
\end{align}
$$
此外假设
$$
\ln \lambda_{t+1}=\gamma \ln\lambda_{t}+\varepsilon_{t+1},\varepsilon_{t+1}\sim N(0,\sigma_{\varepsilon}^{2})
$$
这意味着稳态时 $\ln \bar{\lambda}=0\implies \bar{\lambda}=1$

### 稳态
$$
\begin{align}
\frac{1}{\hat{p}}&=\bar{w}\bar{H}+(\bar{r}-\delta)\bar{K} \\
\bar{C}&=\frac{1}{\hat{p}} \\
1&=\beta(1+\bar{r}+\delta) \\
\frac{\bar{C}}{\bar{w}}&=-\frac{\beta}{B\bar{g}} \\
\bar{r}&=\theta \left( \frac{\bar{K}}{\bar{H}} \right) ^{\theta-1} \\
\bar{w}&=(1-\theta)\left( \frac{\bar{K}}{\bar{H}} \right) ^\theta
\end{align}
$$
### 对数线性化

对数线性化原则为
-  $x_{t}=\bar{x}\cdot \exp[\tilde{x}_{t}]\approx \bar{x}(1+\tilde{x}_{t})$ 
- $\frac{1}{x_{t}}=\frac{1}{\bar{x}}\cdot \exp[-\tilde{x}_{t}]\approx \bar{x}(1-\tilde{x}_{t})$ 
- $x_{t}y_{t}=\bar{x}\bar{y}\exp[\tilde{x}_{t}+\tilde{y}_{t}]\approx \bar{x}\bar{y}(1+\tilde{x}_{t}+\tilde{y}_{t})$ 
- $\frac{x_{t}}{y_{t}}=\frac{\bar{x}}{\bar{y}}\cdot \exp[\tilde{x}_{t}-\tilde{y}_{t}]\approx\frac{\bar{x}}{\bar{y}}(1+\tilde{x}_{t}-\tilde{y}_{t})$

一般均衡模型对数线性化去稳态为
$$
\begin{align}
\bar{K}\tilde{K}_{t+1}-\frac{1}{\bar{p}}\tilde{p}_{t}&=\bar{w}\bar{H}(\tilde{w}_{t}+\tilde{H}_{t})+(1-\delta)\bar{K}\tilde{K}_{t}+\bar{r}\bar{K}(\tilde{r}_{t}+\tilde{K}_{t}) \\
\tilde{C}_{t}+\tilde{p}_{t}&=0 \\
\tilde{w}_{t+1}-\tilde{w}_{t}&=\beta E_{t}(1+\bar{r}\tilde{r}_{t+1}+\delta) \\
... \\

\end{align}
$$

## 铸币税

假设政府增发货币全部用于政府购买而非转移支付。

重定义货币增长率为 $\varphi$，政府购买为 $g_{t}$
$$
\varphi\equiv \frac{M_{t}}{M_{t-1}}\quad g_{t}\equiv \frac{M_{t}-M_{t-1}}{p_{t}}=\hat{g}_{t}\bar{g}
$$
其中 $\bar{g}$ 为平均政府购买，$\hat{g}_{t}$ 为随机过程，满足 $\ln \hat{g}_{t}=\pi \ln \hat{g}_{t-1}+\varepsilon_{t}^g$

此时，CIA 约束为
$$
p_{t}c_{t}\leq m_{t-1}\implies \hat{p}_{t}c_{t}\leq \frac{m_{t-1}}{M_{t-1}} \frac{M_{t-1}}{M_{t}}=\frac{\hat{m}_{t-1}}{\varphi}
$$
消费者一般预算约束为
$$
\begin{align}
p_{t}\{c_{t}+[k_{t+1}-(1-\delta)k_{t}]\}+m_{t}&=p_{t}(w_{t}h_{t}+r_{t}k_{t})+m_{t-1} \\
\hat{p}\{c_{t}+[k_{t+1}-(1-\delta)k_{t}]\}+\hat{m}_{t}&=\hat{p}_{t}(w_{t}h_{t}+r_{t}k_{t})+\frac{m_{t-1}}{M_{t-1}} \frac{M_{t-1}}{M_{t}} \\
c_{t}+k_{t+1}-(1-\delta)k_{t}+\frac{\hat{m}_{t}}{\hat{p}_{t}}&=w_{t}h_{t}+r_{t}k_{t}+\frac{\hat{m}_{t-1}}{\varphi \hat{p}_{t}}
\end{align}
$$
代入 CIA 紧约束可得
$$
k_{t+1}-(1-\delta)k_{t}+\frac{\hat{m}_{t}}{\hat{p}_{t}}=w_{t}h_t+r_{t}k_{t}
$$
消费者最优化问题为
$$
\begin{split}
\max &\ E_{0}\sum_{0}^\infty \beta^t(\ln c_{t}+Bh_{t}) \\
\text{s.t.} &\ k_{t+1}-(1-\delta)k_{t}+\frac{\hat{m}_{t}}{\hat{p}_{t}}=w_{t}h_t+r_{t}k_{t} \\
&\ c_{t}=\frac{\hat{m}_{t-1}}{\varphi\hat{p}_{t}}
\end{split}
$$
Bellman Equation 为
$$
\begin{align}
V(k_{t},\hat{m}_{t-1},\hat{g}_{t})=&\max_{k_{t+1},\hat{m}_{t}} \ln\left( \frac{\hat{m}_{t-1}}{\varphi \hat{p}_{t}} \right)+B\left( \frac{k_{t+1}-(1-\delta)k_{t}+\frac{\hat{m}_{t}}{\hat{p}_{t}}-r_{t}k_{t}}{w_{t}} \right) \\
&+\beta E_{t}V(k_{t+1},\hat{m}_{t},\hat{g}_{t+1})
\end{align}
$$
F.O.C.
$$
\begin{align}
\frac{\partial V_{t}}{\partial k_{t+1}}&= \frac{B}{w_{t}}+\beta E_{t}\frac{\partial V_{t+1}}{\partial k_{t+1}}=0  \\
\frac{\partial V_{t}}{\partial \hat{m}_{t}} &=\frac{B}{\hat{p}_{t}w_{t}}+\beta E_{t}\frac{\partial V_{t+1}}{\partial \hat{m}_{t}}=0
\end{align}
$$
根据包络定理
$$
\begin{align}
\frac{\partial V_{t}}{\partial k_{t}}&= -\frac{B(1-\delta+r_{t})}{w_{t}}&\implies \frac{\partial V_{t+1}}{\partial k_{t+1}}&= -\frac{B(1-\delta+r_{t+1})}{w_{t+1}} \\
\frac{\partial V_{t}}{\partial \hat{m}_{t-1}} &=\frac{1}{\hat{m}_{t-1}}&\implies \frac{\partial V_{t+1}}{\partial \hat{m}_{t}}&=\frac{1}{\hat{m}_{t}} 
\end{align}
$$
代入F.O.C.
$$
\begin{align}
\frac{1}{w_{t}}&=\beta E_{t} \left[ \frac{1-\delta+r_{t+1}}{w_{t+1}} \right] \\
\frac{B}{\hat{p}_{t}w_{t}}&=-\frac{\beta}{\hat{m}_{t}}
\end{align}
$$




