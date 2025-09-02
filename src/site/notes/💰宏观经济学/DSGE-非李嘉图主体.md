---
{"dg-publish":true,"permalink":"/💰宏观经济学/DSGE-非李嘉图主体/","created":"2024-10-12T10:25:03.000+08:00","updated":"2025-09-02T11:09:33.056+08:00"}
---

非李嘉图主体是无法借贷、没有投资（收入全部用于消费）的消费者。假设消费者中比例为 $\omega$ 的部分是李嘉图主体，比例为 $1-\omega$ 的部分是非李嘉图主体。

## 消费者

### 李嘉图消费者
和 [[💰宏观经济学/DSGE Model\|💰宏观经济学/DSGE Model]] 完全一致，均衡条件为
$$
\begin{align}
\frac{1-\gamma}{\gamma} \frac{C_{i,t}}{1-L_{i,t}}&=w_{t} \\
\frac{C_{i,t}}{C_{i,t-1}}&=\beta(1+r_{t}-\delta)
\end{align}
$$
### 非李嘉图消费者
效用最大化问题为
$$
\begin{split}
\max &\ E_{t}\sum_{t=0}^\infty \beta^t U(C_{j,t},O_{j,t}) \\
\text{s.t.} &\ U(C_{j,t},O_{j,t})=\gamma \ln C_{j,t}+\ln(1-\gamma)O_{j,t} \\
&\ O_{j,t}+L_{j,t}\equiv 1\\
&\ C_{j,t}=w_{t}L_{j,t}\\
\end{split}
$$
等价于
$$
\begin{split}
\max &\ E_{t}\sum_{t=0}^\infty \beta^t[\gamma \ln C_{j,t}+(1-\gamma)\ln(1-L_{j,t})] \\
\text{s.t.} &\ C_{j,t}=w_{t}L_{j,t}
\end{split}
$$
Lagrangian is
$$
\begin{align*}
\mathcal{L}=&E_{t} \{ \sum_{t=0}^\infty \beta^t[\gamma \ln C_{j,t}+(1-\gamma)\ln(1-L_{j,t})]+\lambda_{t}[w_{t}L_{j,t}-C_{j,t}] \} 
\end{align*}
$$
F.O.C
$$
\begin{align}
\frac{ \partial \mathcal{L} }{ \partial C_{j,t} } &=\beta^t \left[ \frac{\gamma}{C_{j,t}}-\lambda_{t} \right]=0 \\
\frac{ \partial \mathcal{L} }{ \partial L_{j,t} }&=\beta^t \left[ -\frac{1-\gamma}{1-L_{j,t}}+\lambda_{t}w_{t} \right]=0
\end{align}
$$
which implies
$$
\frac{1-\gamma}{\gamma} \frac{C_{j,t}}{1-L_{j,t}}=w_{t}
$$
### 消费者加总
假设
$$
\begin{align}
C_{t}&\equiv\omega C_{i,t}+(1-\omega)C_{j,t}\\
L_{t}&\equiv\omega L_{i,t}+(1-\omega)L_{j,t} \\
K_{t}&\equiv \omega K_{i,t} \\
I_{t}&\equiv \omega I_{i,t}
\end{align}
$$
## 厂商

和 [DSGE Model]]完全一致

## 一般均衡

$$
\begin{align}
\frac{1-\gamma}{\gamma} \frac{C_{i,t}}{1-L_{i,t}}&=w_{t} \tag{M1}\\
\frac{C_{i,t}}{C_{i,t-1}}&=\beta(1+r_{t}-\delta) \tag{M2} \\
\frac{1-\gamma}{\gamma} \frac{C_{j,t}}{1-L_{j,t}}&=w_{t} \tag{M3} \\
C_{t}&\equiv\omega C_{i,t}+(1-\omega)C_{j,t} \tag{M4}\\
L_{t}&\equiv\omega L_{i,t}+(1-\omega)L_{j,t} \tag{M5}\\
K_{t}&\equiv \omega K_{i,t} \tag{M6}\\
I_{t}&\equiv \omega I_{i,t} \tag{M7} \\
r_{t}&=\alpha A_{t}K_{t}^{\alpha-1}L_{t}^{1-\alpha }=\frac{\alpha Y_{t}}{K_{t}} \tag{M8} \\
w_{t}&=(1-\alpha)A_{t}K_{t}^\alpha L_{t}^{-\alpha}=\frac{(1-\alpha)Y_{t}}{L_{t}} \tag{M9}\\
Y_{t}&=C_{t}+I_{t} \tag{M10}\\
Y_{t}&=A_{t}K_{t}^\alpha L_{t}^{1-\alpha} \tag{M11}\\
I_{i,t}&=K_{i,t+1}-(1-\delta)K_{i,t} \tag{M12}
\end{align}
$$
此外假设
$$
\ln A_{t}=(1-\rho_{A})\ln \bar{A}+\rho_{A}\ln A_{t-1}+\varepsilon_{t}^A\ ,\varepsilon_{t}^A\sim N(0,\sigma_{A}^{2})
$$