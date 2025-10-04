---
{"dg-publish":true,"permalink":"/宏观经济学/DSGE-消费习惯/","created":"2024-10-12T10:25:07.000+08:00","updated":"2025-09-12T18:57:53.491+08:00"}
---

## 消费者

效用最大化问题为
$$
\begin{split}
\max &\ E_{t} \sum_{0}^\infty U(C_{t}-H_{t},O_t) \\
\text{s.t.} &\ U(C_{t}-H_{t},O_{t})=\gamma \ln(C_{t}-H_{t})+(1-\gamma)\ln(O_{t}) \\
&\ O_{t}+L_{t}\equiv 1 \\
&\ H_{t}\equiv \phi C_{t-1} \\
&\ C_{t}+I_{t}=w_{t}L_{t}+r_{t}K_{t}\\
&\ I_{t}=K_{t+1}-(1-\delta)K_{t}
\end{split}
$$
等价于
$$
\begin{split}
\max &\ E_{t}\sum_{t=0}^\infty \beta^t[\gamma \ln (C_{t}-\phi C_{t-1})+\ln(1-\gamma)(1-L_{t})] \\
\text{s.t.} &\ C_{t}+K_{t+1}=w_{t}L_{t}+(1+r_{t}-\delta)K_{t}
\end{split}
$$
Lagrangian is
$$
\begin{align*}
\mathcal{L}=&E_{t} \{ \sum_{t=0}^\infty \beta^t[\gamma \ln (C_{t}-\phi C_{t-1})+\ln(1-\gamma)(1-L_{t})] \\
&{}+\lambda_{t}[w_{t}L_{t}+(1+r_{t}-\delta)K_{t}-C_{t}-K_{t+1}] \} 
\end{align*}
$$
F.O.C
$$
\begin{align*}
\frac{\partial \mathcal{L}}{\partial C_{t}}&=\beta^t\left[ \frac{\gamma}{C_{t}-\phi C_{t-1}}-\lambda_{t} \right]-\beta^{t+1}\frac{\gamma \phi}{C_{t+1}-\phi C_{t}}=0 \tag{1}\\
\frac{\partial \mathcal{L}}{\partial L_{t}}&=\beta^t\left[ -\frac{1-\gamma}{1-L_{t}}+\lambda_{t}w_{t} \right]=0 \tag{2}\\
\frac{\partial \mathcal{L}}{\partial K_{t}}&=\beta^t\lambda_{t}(1+r_{t}-\delta)+\beta^{t-1}\lambda_{{t-1}}(-1)=0 \tag{3}
\end{align*}
$$
又 $(1)(2)$ 可得
$$
\frac{\frac{1-\gamma}{1-L_{t}}}{\frac{\gamma}{C_{t}-\phi C_{t-1}}-\frac{\phi\beta\gamma}{C_{t+1}-\phi C_{t}}}=w_{t}
$$
which in fact is in [[微观经济学/效用最大化\|效用最大化]]
$$
\frac{U_{O,t}}{U_{C,t}}=\frac{P_{O}}{P_{C}}=\frac{w_{t}}{1}
$$
由 $(1)$ 得到欧拉方程再利用 $(3)$ 消去 $\lambda$ 可得
$$
\frac{\frac{1}{C_{t-1}-\phi C_{t-2}}-\frac{\phi\beta}{C_{t}-\phi C_{t-1}}}{\frac{1}{C_{t}-\phi C_{t-1}}-\frac{\phi\beta}{C_{t+1}-\phi C_{t}}}=\beta(1+r_{t}-\delta)
$$
which exactly in [[微观经济学/跨期效用最大化\|跨期效用最大化]]
$$
\frac{U_{C,t-1}}{U_{C,t}}=\beta(1+r_{t}-\delta)
$$
显然，当 $\phi=0$ 上式就退化为 [DSGE Model]]中的结果。

## 厂商

和 [[宏观经济学/DSGE Model\|DSGE Model]] 完全相同

## 一般均衡

和 [DSGE Model]]几乎相同
$$
\begin{align*}
\frac{\frac{1-\gamma}{1-L_{t}}}{\frac{\gamma}{C_{t}-\phi C_{t-1}}-\frac{\phi\beta\gamma}{C_{t+1}-\phi C_{t}}}&=w_{t} \tag{M1}\\
\frac{\frac{1}{C_{t-1}-\phi C_{t-2}}-\frac{\phi\beta}{C_{t}-\phi C_{t-1}}}{\frac{1}{C_{t}-\phi C_{t-1}}-\frac{\phi\beta}{C_{t+1}-\phi C_{t}}}&=\beta(1+r_{t}-\delta)\tag{M2}\\
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