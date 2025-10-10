---
{"dg-publish":true,"permalink":"/宏观经济学/Deterministic Problem/"}
---

## Consumption-Saving Problem

The problem is
$$
\begin{split}
\max_{\{c_{t},k_{t+1}\}_{t=0}^\infty} &\ \sum_{t=0}^\infty \beta^t u(c_{t}) \\
\text{s.t.} &\ k_{t+1}=(1+r)k_{t}-c_{t} \\
&\ k_{t+1}\geq 0 \\
&\ k_{0}=k
\end{split}
$$
一般地，消费者通过选择消费序列 $\{c_{t}\}_{t=0}^\infty$ 和资本序列 $\{k_{t+1}\}_{t=0}^\infty$ 最大化终身效用。

特别地，不同于静态最优化方法找到一个最优解，动态最优化方法试图找到一个最优函数。定义**政策函数**（policy function）将资本序列 $\{k_{t}\}_{t=0}^\infty$ 映射为最优消费序列 $\{c_{t}\}_{t=0}^\infty$ ，使得 $h(k_{t})=c_{t}$，将其代回目标函数可以得到值函数。

序列的映射可以看作如下递归过程：
1. 输入 $k_{0}$，设定 $c_{0}$，由约束方程得到 $k_{1}$，然后迭代，对应政策函数 $h(k_{0})=c_{0}$；
2. 输入 $k_{0}$，设定 $k_{1}$，由约束方程得到 $c_{0}$，然后迭代，政策函数是 $h(k_{0})=k_{1}$
约束方程的存在减少自由度，所以可以任选 $c_{t}$ 或 $k_{t+1}$ 作为控制变量，这里采用后者。
无论采用哪种视角，政策函数的参数都是状态变量 $k_{0}$，因此值函数的变量也是 $k_{0}$。

值函数可以写为
$$
\begin{align}
V(k_{0})&=\max_{\{k_{t+1}\}_{t=0}^\infty} \sum_{t=0}^\infty \beta^t u(c_{t}) \\
&=\max_{\{k_{t+1}\}_{t=0}^\infty} u(c_{0})+\sum_{t=1}^\infty \beta^t u(c_{t}) \\
&=\max_{\{k_{t+1}\}_{t=0}^\infty} u(c_{0})+\beta\sum_{t=1}^\infty \beta^{t-1} u(c_{t}) \\
&=\max_{\{k_{t+1}\}_{t=0}^\infty} u(c_{0})+\beta V(k_{1}) \quad\text{ (Bellman Equation)}
\end{align}
$$
代入约束条件
$$
V(k_{0})=\max_{\{k_{t+1}\}_{t=0}^\infty} u((1+r)k_{0}-k_{1})+\beta V(k_{1})
$$
F.O.C.
$$
\frac{ \partial V(k_{0}) }{ \partial k_{1} }=-\frac{ \partial u }{ \partial c_{0} }+\beta \frac{ \partial V(k_{1}) }{ \partial k_{1} } =0
$$
根据包络定理
$$
\frac{ \partial V(k_{0}) }{ \partial k_{0} }=\frac{ \partial [u((1+r)k_{0}-k_{1})+\beta V(k_{1})] }{ \partial k_{0} }=(1+r)\frac{ \partial u }{ \partial c_{0} } 
$$
One Step Forward
$$
\frac{ \partial V(k_{1}) }{ \partial k_{1} }=(1+r)\frac{ \partial u }{ \partial c_{1} }
$$
代回F.O.C.得到 Euler Equation
$$
\frac{\frac{ \partial u }{ \partial c_{0} }}{\frac{ \partial u }{ \partial c_{1} } }=\beta(1+r) 
$$
代入最优政策函数 $h(k_{t})=k_{t+1}$ 就可得得到 $h$ 的显式解。


## General Problem

$$
\begin{split}
\max_{{\{x_{s},y_{s}\}}_{s=t}^\infty} &\ \sum_{s=t}^\infty \beta^{s-t}F(x_{s},y_{s}) \\
\text{s.t.} &\ x_{s+1}=G(x_{s},y_{s})\quad \forall s\geq t 
\end{split}
$$
这里将从 0 期至无穷期的优化问题一般化为 t 期至无穷期的最优化问题，$x_{s}$ 是状态变量，$y_{s}$ 是控制变量，$x_{s+1}$ 由约束方程决定，故政策函数为 $h(x_{s})=y_{s}$

Bellman Equation可以写为
$$
\begin{align}
V(x_{t})&=\max_{\{y_{s}\}_{s=t}^\infty} F(x_{t},y_{t})+\sum_{s=t+1}^\infty \beta^{s-t}F(x_{s},y_{s}) \\
&=\max_{\{y_{s}\}_{s=t}^\infty} F(x_{t},y_{t})+\beta\sum_{s=t+1}^\infty \beta^{s-(t+1)}F(x_{s},y_{s}) \\
&=\max_{\{y_{s}\}_{s=t}^\infty} F(x_{t},y_{t})+\beta V(x_{t+1}) \\
\end{align}
$$
F.O.C.
$$
\frac{ \partial V(x_{t}) }{ \partial y_{t} }=\frac{ \partial F(x_{t},y_{t}) }{ \partial y_{t} } +\beta \frac{ \partial V(x_{t+1}) }{ \partial x_{t+1} } \frac{ \partial G(x_{t},y_{t}) }{ \partial y_{t} }=0
$$
根据包络定理
$$
\frac{ \partial V(x_{t}) }{ \partial x_{t} } =\frac{ \partial F(x_{t},y_{t}) }{ \partial x_{t} }+\beta \frac{ \partial V(x_{t+1}) }{ \partial x_{t+1} } \frac{ \partial G(x_{t},y_{t}) }{ \partial x_{t} } 
$$
假如通过合理设定控制变量使得 $\frac{ \partial G(x_{t},y_{t}) }{ \partial x_{t} }=0$，one step forward
$$
\frac{ \partial V(x_{t+1}) }{ \partial x_{t+1} } =\frac{ \partial F(x_{t+1},y_{t+1}) }{ \partial x_{t+1} } 
$$
代回F.O.C.
$$
-\frac{\frac{ \partial F(x_{t},y_{t}) }{ \partial x_{t} }}{\frac{ \partial F(x_{t+1},y_{t+1}) }{ \partial x_{t+1} } }=\beta \frac{ \partial G(x_{t},y_{t}) }{ \partial y_{t} } 
$$
代入政策函数 $h(x_{t})=y_{t}$ 可以解得显式解。

## 两个控制变量的例子

$$
\begin{split}
\max &\ \sum_{s=t}^\infty \beta^s u(c_{s},l_{s}) \\
\text{s.t.} &\ k_{t+1}=(1-\delta)k_{t}+i_{t} \\
&\ y_{t}=f(k_{t},l_{t})\geq c_{t}+i_{t} \\
&\ l_{t}\in [0,1]
\end{split}
$$
消费和劳动影响效用，劳动以时间衡量，时间标准化为 1，第二个约束显然是紧的，否则增加消费总可以提高效用，因此问题可以改写为
$$
\begin{split}
\max &\ \sum_{s=t}^\infty \beta^s u(c_{s},l_{s}) \\
\text{s.t.} &\ k_{t+1}=(1-\delta)k_{t}+f(k_{t},l_{t})-c_{t} \\
&\ l_{t}\in [0,1]
\end{split}
$$
状态变量为 $k_{t}$，控制变量为 $k_{t+1}$ 和 $l_{t}$，由约束方程得到 $c_{t}$

Bellman Equation 写为
$$
\begin{align}
V(k_{t})&=\max_{\{k_{s+1},l_{s}\}_{s=t}^\infty} u(c_{t},l_{t})+\beta V(k_{t+1}) \\
&=\max_{\{k_{s+1},l_{s}\}_{s=t}^\infty} u([-k_{t+1}+(1-\delta)k_{t}+f(k_{t},l_{t})],l_{t})+\beta V(k_{t+1}) 
\end{align}
$$
F.O.C.
$$
\begin{align}
\frac{ \partial V(k_{t}) }{ \partial k_{t+1} }&=-\frac{ \partial u(c_{t},l_{t}) }{ \partial c_{t} }+\beta \frac{ \partial V(k_{t+1}) }{ \partial k_{t+1} }=0  \\
\frac{ \partial V(k_{t}) }{ \partial l_{t} }&=\frac{ \partial u(c_{t},l_{t}) }{ \partial c_{t} }\frac{ \partial f(k_{t},l_{t}) }{ \partial l_{t} }+\frac{ \partial u(c_{t},l_{t}) }{ \partial l_{t} }=0
\end{align}
$$
根据包络定理
$$
\frac{ \partial V(k_{t}) }{ \partial k_{t} }=\frac{ \partial u(c_{t},l_{t}) }{ \partial c_{t} }[(1-\delta)+\frac{ \partial f(k_{t},l_{t}) }{ \partial k_{t} } ]
$$
one step forward
$$
\frac{ \partial V(k_{t+1}) }{ \partial k_{t+1} }=\frac{ \partial u(c_{t+1},l_{t+1}) }{ \partial c_{t+1} }[(1-\delta)+\frac{ \partial f(k_{t+1},l_{t+1}) }{ \partial k_{t+1} }]
$$
代回F.O.C.得到
$$
\beta\frac{ \partial u(c_{t+1},l_{t+1}) }{ \partial c_{t+1} }[(1-\delta)+\frac{ \partial f(k_{t+1},l_{t+1}) }{ \partial k_{t+1} }]\cdot\frac{ \partial f(k_{t},l_{t}) }{ \partial l_{t} }+\frac{ \partial u(c_{t},l_{t}) }{ \partial l_{t} }=0
$$
