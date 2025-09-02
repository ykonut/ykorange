---
{"dg-publish":true,"permalink":"/💰宏观经济学/经济波动/DSGE-税收/","created":"2024-10-12T10:25:01.000+08:00","updated":"2025-08-27T16:00:04.292+08:00"}
---

考虑一次性税收，预算约束为
$$
C_t+S_t=Y_t-T_t
$$
考虑各种比例税，预算约束为
$$
\begin{align}
C_{t}+S_{t}&=(1-\tau^y)Y_{t}-\tau^c_{t} C_{t}-\tau^s S_{t} \\
(1+\tau^c_{t})C_{t}+(1+\tau^s)S_{t}&=(1-\tau^y)Y_{t}
\end{align}
$$
其中 $\tau^{c,s,y}$ 分别为消费税率、储蓄税率、所得税率。

考虑消费税、劳动所得税、资本利得税，预算约束为
$$
\begin{align}
C_{t}+I_{t}&=w_{t}L_{t}+r_{t}K_{t}+G_{t}-\tau^l_{t}w_{t}L_{t}-\tau^k_{t}(r_{t}-\delta)K_{t} \\
(1+\tau^c_{t})C_{t}+I_{t}&=(1-\tau^l_{t})w_{t}L_{t}+[(1-\tau^k_{t})r_{t}+\tau^k_{t}\delta]K_{t}+G_{t}
\end{align}
$$
> 注意：资本利得税只对资本增值的部分而非全部收入征收。

## 消费者

效用最大化问题为
$$
\begin{split}
\max &\ E_{t}\sum_{t=0}^\infty \beta^t U(C_{t},O_{t}) \\
\text{s.t.} &\ U(C_{t},O_{t})=\gamma \ln C_{t}+\ln(1-\gamma)O_{t} \\
&\ O_{t}+L_{t}\equiv 1\\
&\ (1+\tau^c_{t})C_{t}+I_{t}=(1-\tau^l_{t})w_{t}L_{t}+[(1-\tau^k_{t})r_{t}+\tau^k_{t}\delta]K_{t}+G_{t}\\
&\ I_{t}=K_{t+1}-(1-\delta)K_{t}
\end{split}
$$
等价于
$$
\begin{split}
\max &\ E_{t}\sum_{t=0}^\infty \beta^t[\gamma \ln C_{t}+(1-\gamma)\ln(1-L_{t})] \\
\text{s.t.} &\ (1+\tau^c_{t})C_{t}+K_{t+1}=(1-\tau^l_{t})w_{t}L_{t}+[1+(1-\tau^k_{t})(r_{t}-\delta)]K_{t}+G_{t}
\end{split}
$$
Lagrangian is
$$
\begin{align*}
\mathcal{L}=&E_{t} \{ \sum_{t=0}^\infty \beta^t[\gamma \ln C_{t}+(1-\gamma)\ln(1-L_{t})] \\
&{}+\lambda_{t}[(1-\tau^l_{t})w_{t}L_{t}+[1+(1-\tau^k_{t})(r_{t}-\delta)]K_{t}+G_{t}-(1+\tau^c_{t})C_{t}-K_{t+1}] \}
\end{align*}
$$
F.O.C.
$$
\begin{align*}
\frac{\partial \mathcal{L}}{\partial C_{t}}&=\beta^t\left[ \frac{\gamma}{C_{t}}-\lambda_{t}(1+\tau^c_{t}) \right]=0 \tag{1}\\
\frac{\partial \mathcal{L}}{\partial L_{t}}&=\beta^t\left[ -\frac{1-\gamma}{1-L_{t}}+\lambda_{t}(1-\tau^l_{t})w_{t} \right]=0 \tag{2}\\
\frac{\partial \mathcal{L}}{\partial K_{t}}&=\beta^t\lambda_{t}[1+(1-\tau^k_{t})(r_{t}-\delta)]+\beta^{t-1}\lambda_{{t-1}}(-1)=0 \tag{3}
\end{align*}
$$
由 $(1)(2)$ 可得
$$
\frac{\frac{1-\gamma}{1-L_{t}}}{\frac{\gamma}{C_{t}}}=\frac{(1-\tau^l_{t})w_{t}}{1+\tau^c_{t}}\implies \frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}=\frac{(1-\tau^l_{t})w_{t}}{1+\tau^c_{t}}
$$
which in fact is in [[⚖️微观经济学/效用最大化\|效用最大化]]
$$
\frac{U_{O}}{U_{C}}=\frac{P_{O}}{P_{C}}=\frac{(1-\tau^l_{t})w_{t}}{1+\tau^c_{t}}
$$
这表明劳动所得税使得闲暇的机会成本降低了，消费税使得消费的成本提高了。

由 $(1)$ 得到欧拉方程再利用 $(3)$ 消去 $\lambda$ 可得
$$
\frac{(1+\tau^c_{t})C_{t}}{(1+\tau_{t-1}^c)C_{t-1}}=\beta[1+(1-\tau^k{t})(r_{t}-\delta)]
$$
which exactly in [[⚖️微观经济学/跨期效用最大化\|跨期效用最大化]]
$$
\frac{U_{C,t-1}}{U_{C,t}}=\beta[1+(1-\tau^k_{t})(r_{t}-\delta)]
$$
## 厂商

和 [[💰宏观经济学/经济波动/DSGE Model\|💰宏观经济学/经济波动/DSGE Model]] 完全一致

## 政府

假设收支平衡，税收全部用于转移支付。
$$
\tau^c_{t}C_{t}+\tau^l_{t}w_{t}L_{t}+\tau^k_{t}(r_{t}-\delta)K_{t}=G_{t}
$$
## 一般均衡

$$
\begin{align*}
\frac{1-\gamma}{\gamma} \frac{C_{t}}{1-L_{t}}&=\frac{(1-\tau^l_{t})w_{t}}{1+\tau^c_{t}} \tag{M1}\\
\frac{(1+\tau^c_{t})C_{t}}{(1+\tau_{t-1}^c)C_{t-1}}&=\beta[1+(1-\tau^k_{t})(r_{t}-\delta)] \tag{M2}\\
r_{t}&=\alpha A_{t}K_{t}^{\alpha-1}L_{t}^{1-\alpha }=\frac{\alpha Y_{t}}{K_{t}} \tag{M3} \\
w_{t}&=(1-\alpha)A_{t}K_{t}^\alpha L_{t}^{-\alpha}=\frac{(1-\alpha)Y_{t}}{L_{t}} \tag{M4}\\
Y_{t}&=C_{t}+I_{t} \tag{M5}\\
Y_{t}&=A_{t}K_{t}^\alpha L_{t}^{1-\alpha} \tag{M6}\\
I_{t}&=K_{t+1}-(1-\delta)K_{t} \tag{M7}
\end{align*}
$$
此外假设
$$
\ln A_{t}=(1-\rho_{A})\ln \bar{A}+\rho_{A}\ln A_{t-1}+\varepsilon_{t}^A\ ,\varepsilon_{t}^A\sim N(0,\sigma_{A}^{2})
$$


