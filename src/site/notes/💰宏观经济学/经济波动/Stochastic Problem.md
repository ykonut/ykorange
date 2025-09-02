---
{"dg-publish":true,"permalink":"/💰宏观经济学/经济波动/Stochastic Problem/","created":"2024-10-12T10:24:48.000+08:00","updated":"2024-10-12T10:24:48.000+08:00"}
---


## Consumption-Saving Problem

The problem is
$$
\begin{split}
\max_{\{c_{t},k_{t+1}\}_{t=0}^\infty} &\ E_{0}[\sum_{t=0}^\infty \beta^t \varepsilon_{t} u(c_{t})] \\
\text{s.t.} &\ k_{t+1}=(1+r)k_{t}-c_{t} \\
&\ k_{t+1}\geq 0 \\
&\ k_{0}=k
\end{split}
$$
假设由一个偏好冲击序列 $\{\varepsilon_{t}\}_{t=0}^\infty$ ，其中 $\varepsilon_{t}$ 服从 Markov process，也就是说 $\varepsilon_{t}$ 的分布只取决于 $\varepsilon_{t-1}$ 的值。注意 $E_{0}$ 指的是 conditional on $0$，而不是 $0$ 期的期望。

此时有两个状态变量 $k_{t}$ 和 $\varepsilon_{t}$，Bellman Equation 为
$$
\begin{align}
V(k_{0},\varepsilon_{0})&=\max_{\{k_{t+1}\}_{t=0}^\infty} \sum_{t=0}^\infty \beta^t E_{t}[\varepsilon_{t}u(c_{t})] \\
&=\max_{\{k_{t+1}\}_{t=0}^\infty} \varepsilon_{0}u(c_{0})+\sum_{t=1}^\infty \beta^t E_{t}[\varepsilon_{t}u(c_{t})] \\
&=\max_{\{k_{t+1}\}_{t=0}^\infty} \varepsilon_{0} u(c_{0})+\beta \sum_{t=1}^\infty \beta^{t-1} E_{t}[\varepsilon_{t}u(c_{t})] \\
&=\max_{\{k_{t+1}\}_{t=0}^\infty} \varepsilon_{0}u(c_{0})+\beta E_{1}V(k_{1},\varepsilon_{1})
\end{align}
$$
F.O.C.
$$
\frac{ \partial V(k_{0},\varepsilon_{0}) }{ \partial k_{1} }=-\varepsilon_{0}\frac{ \partial u(c_{0}) }{ \partial c_{0} }+\beta E_{1}\frac{ \partial V(k_{1},\varepsilon_{1}) }{ \partial k_{1} }=0
$$
根据包络定理
$$
\frac{ \partial V(k_{0},\varepsilon_{0}) }{ \partial k_{0} }=\varepsilon_{0}\frac{ \partial u(c_{0}) }{ \partial c_{0} }(1+r)
$$
one step forward
$$
\frac{ \partial V(k_{1},\varepsilon_{1}) }{ \partial k_{1} }=\varepsilon_{1}\frac{ \partial u(c_{1}) }{ \partial c_{1} }(1+r)
$$
代回F.O.C.可得
$$
\varepsilon_{0}\frac{ \partial u(c_{0}) }{ \partial c_{0} }=\beta(1+r)E_{1}\left( \varepsilon_{1}\frac{ \partial u(c_{1}) }{ \partial c_{1} }  \right)
$$
代入政策函数 $h(k_{0},\varepsilon_{0})=c_{0}$ 可得显式解

## Real Business-Cycle Model