---
{"dg-publish":true,"permalink":"/💰宏观经济学/DSGE-公共支出/","created":"2024-10-12T10:25:08.000+08:00","updated":"2025-09-02T11:09:35.142+08:00"}
---

## 消费者

假设消费者同时受益于私人消费和公共消费。

效用最大化问题为
$$
\begin{split}
\max_{\{C_{P,t},L_{t},K_{t}\}} &\ E_{t}\sum_{t=0}^\infty \beta^t U(B_{t},O_{t}) \\
\text{s.t.} &\ U(B_{t},O_{t})=\gamma \ln B_{t}+\ln(1-\gamma)O_{t} \\
&\ B_{t}=[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta} \\
&\ O_{t}+L_{t}\equiv 1\\
&\ (1+\tau_{t}^c)C_{P,t}+I_{t}=(1-\tau_{t}^l)w_{t}L_{t}+[(1-\tau_{t}^k)r_{t}+\tau_{t}^k\delta]K_{t}+G_{t}\\
&\ I_{t}=K_{t+1}-(1-\delta)K_{t}
\end{split}
$$
等价于
$$
\begin{split}
\max &\ E_{t}\sum_{t=0}^\infty \beta^t\left\{\gamma \ln [\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}+(1-\gamma)\ln(1-L_{t})\right\} \\
\text{s.t.} &\ (1+\tau_{t}^c)C_{P,t}+K_{t+1}=(1-\tau_{t}^l)w_{t}L_{t}+[1+(1-\tau^k_{t})(r_{t}-\delta)]K_{t}+G_{t}
\end{split}
$$
Lagrangian is
$$
\begin{align*}
\mathcal{L}=&E_{t} ( \sum_{t=0}^\infty \beta^t\left\{\gamma \ln [\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}+(1-\gamma)\ln(1-L_{t})\right\} \\
&{}+\lambda_{t}[(1-\tau_{t}^l)w_{t}L_{t}+[1+(1-\tau^k_{t})(r_{t}-\delta)]K_{t}+G_{t}-(1+\tau_{t}^c)C_{P,t}-K_{t+1}] )
\end{align*}
$$
F.O.C.
$$
\begin{align*}
\frac{\partial \mathcal{L}}{\partial C_{P,t}}&=\beta^t\left[ \frac{\gamma\omega C_{P,t}^{\eta-1}}{[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}}-\lambda_{t}(1+\tau_{t}^c) \right]=0 \tag{1}\\
\frac{\partial \mathcal{L}}{\partial L_{t}}&=\beta^t\left[ -\frac{1-\gamma}{1-L_{t}}+\lambda_{t}(1-\tau_{t}^l)w_{t} \right]=0 \tag{2}\\
\frac{\partial \mathcal{L}}{\partial K_{t}}&=\beta^t\lambda_{t}[1+(1-\tau^k_{t})(r_{t}-\delta)]+\beta^{t-1}\lambda_{{t-1}}(-1)=0 \tag{3}
\end{align*}
$$
由 $(1)(2)$ 可得
$$
\frac{\frac{1-\gamma}{1-L_{t}}}{\frac{\gamma\omega C_{P,t}^{\eta-1}}{[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}}}=\frac{(1-\tau_{t}^l)w_{t}}{1+\tau_{t}^c}\implies \frac{1-\gamma}{\gamma} \frac{[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}}{(1-L_{t})\gamma\omega C_{P,t}^{\eta-1}}=\frac{(1-\tau_{t}^l)w_{t}}{1+\tau_{t}^c}
$$
由 $(1)$ 得到欧拉方程再利用 $(3)$ 消去 $\lambda$ 可得
$$
\frac{\frac{C_{P,t-1}^{\eta-1}}{(1+\tau^c_{t-1})[\omega C_{P,t-1}^\eta+(1-\omega)C_{G,t-1}^\eta]^ \frac{1}{\eta}}}{\frac{C_{P,t}^\eta}{(1+\tau_{t}^c)[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}}}=\beta[1+(1-\tau^k{t})(r_{t}-\delta)]
$$
## 厂商

和 [[💰宏观经济学/DSGE Model\|💰宏观经济学/DSGE Model]] 完全一致

## 政府

$$
\tau_{t}^cC_{P,t}+\tau_{t}^lw_{t}L_{t}+\tau^k_{t}(r_{t}-\delta)K_{t}=G_{t}+C_{G,t}
$$

## 一般均衡

$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}}{(1-L_{t})\gamma\omega C_{P,t}^{\eta-1}}&=\frac{(1-\tau_{t}^l)w_{t}}{1+\tau_{t}^c} \tag{M1}\\
\frac{\frac{C_{P,t-1}^{\eta-1}}{(1+\tau^c_{t-1})[\omega C_{P,t-1}^\eta+(1-\omega)C_{G,t-1}^\eta]^ \frac{1}{\eta}}}{\frac{C_{P,t}^\eta}{(1+\tau_{t}^c)[\omega C_{P,t}^\eta+(1-\omega)C_{G,t}^\eta]^ \frac{1}{\eta}}}&=\beta[1+(1-\tau^k{t})(r_{t}-\delta)] \tag{M2}\\
r_{t}&=\alpha A_{t}K_{t}^{\alpha-1}L_{t}^{1-\alpha }=\frac{\alpha Y_{t}}{K_{t}} \tag{M3} \\
w_{t}&=(1-\alpha)A_{t}K_{t}^\alpha L_{t}^{-\alpha}=\frac{(1-\alpha)Y_{t}}{L_{t}} \tag{M4}\\
Y_{t}&=C_{P,t}+C_{G,t}+I_{t} \tag{M5}\\
Y_{t}&=A_{t}K_{t}^\alpha L_{t}^{1-\alpha} \tag{M6}\\
I_{t}&=K_{t+1}-(1-\delta)K_{t} \tag{M7}
\end{align*}
$$
此外假设
$$
\ln A_{t}=(1-\rho_{A})\ln \bar{A}+\rho_{A}\ln A_{t-1}+\varepsilon_{t}^A\ ,\varepsilon_{t}^A\sim N(0,\sigma_{A}^{2})
$$

