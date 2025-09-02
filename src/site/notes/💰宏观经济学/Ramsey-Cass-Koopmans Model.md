---
{"dg-publish":true,"permalink":"/💰宏观经济学/Ramsey-Cass-Koopmans Model/","created":"2024-10-12T10:24:46.000+08:00","updated":"2024-10-12T10:24:46.000+08:00"}
---


该模型旨在将消费（储蓄）选择纳入最优化的框架。
## 家庭

时间：无限期，连续型

代表性家庭瞬时(instantaneous)效用函数为
$$
u(c(t))
$$
假设瞬时效用函数满足：
- 二阶连续可微
- 严格递增
- 严格凹
-  $\lim\limits_{c\to 0}u'(c)=\infty$ 且 $\lim\limits_{c\to \infty}u'(c)=0$

$t=0$ 期家庭期望效用函数为
$$
U(0)=\int_{0}^{\infty} e^{-\rho t}u(c(t))L(t) \, \mathrm{d}t=\int_{0}^{\infty} e^{-(\rho-n)t}u(c(t)) \, \mathrm{d}t \quad \text{where }\rho>n
$$
其中：
- $\rho$ 为效用贴现率
- $c(t)\equiv \frac{C(t)}{L(t)}$ 为人均消费
- $L(t)=e^{nt}L(0)$ 且 $L(0)\equiv1$

> [!NOTE]
> 若时间离散则期望效用函数为 $U(0)=\sum\limits_{t=0}^{\infty}\beta^tu(c(t))$

家庭预算约束为
$$
\dot{\mathcal{A}}(t)\equiv r(t)\mathcal{A}(t)+w(t)L(t)-c(t)L(t)
$$
其中：
- $\mathcal{A}(t)$ 为总资产(asset)
- $r(t)$ 为利率
- $w(t)$ 为工资

定义人均资产 $a(t)\equiv \frac{\mathcal{A}(t)}{L(t)}$ ，从而有
$$
\dot{\mathcal{A}}(t)=\frac{\mathrm{d} a(t)L(t)}{\mathrm{d} t}=\dot{a}(t)L(t)+a(t)\dot{L}(t) 
$$
家庭预算约束可以改写为
$$
\dot{a}(t)=[r(t)-n]a(t)+w(t)-c(t)
$$
> [!NOTE]
> 若不考虑人口增长为
> $$
> \dot{a}(t)=r(t)a(t)+w(t)-c(t)
> $$
> 若考虑外生技术进步为
> $$
> \dot{a}(t)=[r(t)-n-g]a(t)+w(t)-c(t)
> $$
> 若考虑税率为 $\tau$ 的资本所得税为
> $$
> \dot{a}(t)=[(1-\tau) r(t)-n]a(t)+w(t)-c(t)
> $$
> 若考虑税率为 $\tau$ 的收入所得税为
> $$
> \dot{a}(t)=[(1-\tau)r(t)-n]a(t)+(1-\tau)w(t)-c(t)
> $$

## 厂商

类似 [[💰宏观经济学/Solow Model\|Solow Model]] 当中的假设（不考虑技术进步），总量生产函数为
$$
Y(t)=F(K(t),L(t))
$$
人均生产函数为
$$
y(t)\equiv \frac{Y(t)}{L(t)}=f(k(t))
$$
利润最大化问题为（产品作为计价物品）
$$
\max_{K(t),L(t)} F(K(t),L(t))-R(t)K(t)-w(t)L(t)
$$
最优化条件为
$$
\begin{align}
F_{K}(K(t),L(t)) & =R(t) \\
F_{L}(K(t),L(t)) & =w(t)
\end{align}
$$
根据[[⚖️微观经济学/数理经济学/齐次函数#欧拉定理\|齐次函数#欧拉定理]]可知
$$
\begin{align}
F_{K}(K,L) & =f'(k) \\
F_{L}(K,L) & =f(k)-f'(k)k
\end{align}
$$
最优化条件可以改写为
$$
\begin{align}
R(t) & =f'(k(t)) \\
w(t) & =f(k(t))-f'(k(t))k(t)
\end{align}
$$
## 市场出清

$$
\begin{align}
a(t) & =k(t) \\
r(t) & =R(t)-\delta
\end{align}
$$
> [!NOTE]
> 可以这样理解，资产(asset)不会折旧，资本(capital)会折旧，资产的收益 $r(t)$ 和资本的收益 $R(t)-\delta$ 必定相等。
## 均衡

**Definition** A competitive equilibrium of the Ramsey economy consists of paths $\{C (t),K (t),w (t), R (t)\}_{t=0}^\infty$, such that the representative household maximizes its utility given initial capital stock $K(0)$ and the time path of prices $\{ w(t),R(t) \}_{t=0}^\infty$, and all markets clear.

$$
\begin{align}
\max_{c(t)} &\ U(0)=\int_{0}^{\infty} e^{-(\rho-n)t}u(c(t)) \, \mathrm{d}x \\
\text{s.t.} &\ \dot{a}(t)=[r(t)-n]a(t)+w(t)-c(t) \\
&\ \lim_{t\to \infty}a(t)\exp\left[ -\int_{0}^{t} (r(s)-n) \, \mathrm{d}s  \right]\geq 0
\end{align}
$$
> [!NOTE]
> 第二条约束称为 no-ponzi-game 条件，意味在无穷期资产的现值非负。注意其和
> $$
> a(t)\exp\left[ -\int_{0}^{t} (r(s)-n) \, \mathrm{d}s  \right]\geq 0
> $$
> 的区别，前者只要求资产现值在无穷期趋近于非负，可以有借贷行为；后者相当于要求资产现值在任意期都非负，不能有借贷行为。
> 
> 在最优化过程中并不直接处理这条约束，而是求出结果后再验证是否满足约束。

该问题的现值Hamiltonian function 为（see [[💰宏观经济学/最优控制理论\|最优控制理论]]）
$$
\hat{H}(a,c,\mu)=u(c(t))+\mu(t) \{ [r(t)-n]a(t)+w(t)-c(t) \}
$$
Maximum Principle
$$
\begin{align}
\frac{\partial \hat{H}(a,c,\mu)}{\partial c} & =0 &\implies& u'(c(t))=\mu(t) \tag{1}\\
\frac{\partial \hat{H}(a,c,\mu)}{\partial a} & = -\dot{\mu}(t)+(\rho-n) \mu(t) &\implies& \frac{\dot{\mu}(t)}{\mu(t)}=\rho-r(t) \tag{2}\\
\frac{\partial \hat{H}(a,c,\mu)}{\partial \mu}&=\dot{a}(t) \tag{3}\\
\lim_{t\to \infty}[e^{-(\rho-n)t}\mu(t)a(t)] & =0 \tag{4}
\end{align}
$$
根据(1)可得
$$
\frac{\dot{\mu}(t)}{\mu(t)}=\frac{\mathrm{d} \ln u'(c(t))}{\mathrm{d} t}=\frac{1}{u'(c(t))}\frac{\mathrm{d}u'(c(t))}{\mathrm{d} c} \frac{\mathrm{d} c(t)}{\mathrm{d} t}  =\frac{u''(c(t))}{u'(c(t))}c(t) \frac{\dot{c}(t)}{c(t)}
$$
瞬时效用函数的相对[[⚖️微观经济学/风险规避系数\|风险规避系数]] $\theta$ 的定义为
$$
\theta\equiv -c(t) \frac{u''(c(t))}{u'(c(t))}
$$
结合(2)可得**欧拉方程**
$$
\frac{\dot{c}(t)}{c(t)}=\frac{r(t)-\rho}{\theta}
$$
> [!NOTE]
> 是否考虑人口增长率没有影响；
> 若考虑税率为 $\tau$ 的资本所得税**或**收入所得税为
> $$
> \frac{\dot{c}(t)}{c(t)}=\frac{(1-\tau)r(t)-\rho}{\theta}
> $$

代入利润最大化条件、市场出清条件可得
$$
\frac{\dot{c}(t)}{c(t)}=\frac{f'(k)-\delta-\rho}{\theta}
$$
接下来验证约束条件：对(2)积分并代入(1)
$$
\begin{align}
\mu(t) & =\mu(0)\exp\left( \int_{0}^{t} (\rho-r(s)) \, \mathrm{d}s  \right) \\
 & =u'(c(0))\exp\left( -\int_{0}^{t} (r(s)-\rho) \, \mathrm{d}s  \right)
\end{align}
$$
代入横截条件(transversality condition)
$$
\begin{align}
0 & =\lim_{t\to \infty}\left[ e^{-(\rho-n)t}a(t)u'(c(0))\exp\left( -\int_{0}^{t} (r(s)-\rho) \, \mathrm{d}s  \right) \right] \\
0 & =\lim_{t\to \infty}\left[ a(t)\exp\left( -\int_{0}^{t} (r(s)-n) \, \mathrm{d}s  \right) \right]
\end{align}
$$
因此no-Ponzi game 条件满足，相当于无限期资产现值必为零（花光了）

> [!NOTE]
> 如果考虑社会计划者经济，相当于约束条件自动满足市场出清条件：
> $$
> \begin{align}\dot{k}(t) & =[f'(k)-\delta-n]k(t)+[f(k(t))-kf'(k(t))]-c(t) \\
> & =f(k(t))-(n+\delta)k(t)-c(t)
> \end{align}
> $$
> 重复上述最优化过程可得同样的**欧拉方程**
> $$
> \frac{\dot{c}(t)}{c(t)}=\frac{f'(k)-\delta-\rho}{\theta}
> $$
> 如果考虑外生技术进步为
> $$
> \frac{\dot{c}(t)}{c(t)}=\frac{f'(k)-\delta-\rho}{\theta}-g
> $$

## 稳态

在稳态下即 $\dot{c}(t)=\dot{k}(t)=0$ 时，资本劳动比 $k^*$ 取决于
$$
f'(k^*)=\rho+\delta
$$
- 即使考虑外生技术进步，$k^*$ 也只取决于 $(\rho,\delta,g)$；
- 在 [[💰宏观经济学/Solow Model\|Solow Model]] 中 $k^*$ 取决于 $(s,n,g,\delta)$
- 这里核心特点在于 $n$ 对稳态没有影响，更符合现实。

类似地，稳态劳均消费 $c^*$ 取决于
$$
c^*=f(k^*)-(n+\delta)k^*
$$
此时稳态储蓄率相当于
$$
s^*\equiv \frac{f(k^*)-c^*}{f(k^*)}=\frac{(n+\delta)k^*}{f(k^*)}
$$
这和 [[💰宏观经济学/Solow Model\|Solow Model]] （不考虑技术进步）的固定储蓄率完全一致。


---
## 家庭行为

假设 $t$ 期的人口为 $L(t)$，增长率为常数 $n$，即 $L(t)=L(0)e^{nt}$

家庭的个数为常数 $H$，即 $t$ 期每个家庭有 $\frac{L(t)}{H}$ 人

初期资本存量为 $K(0)$，即初期家庭资本存量为 $\frac{K(0)}{H}$

**瞬时效用函数**为 CRRA 效用函数
$$
u(\tilde{c}(t))=\frac{\tilde{c}(t)^{1-\theta}}{1-\theta} ,\theta>0,\theta\neq 1
$$
其中 $\tilde{c}(t)=c(t)A(t)=\frac{C(t)}{L(t)}$ 表示单人的消费

**家庭效用函数**为
$$
\begin{align}
U & =\int_{0}^\infty e^{-\rho t}u(\tilde{c}(t)) \frac{L(t)}{H} \, dt  \\
& =\int_{0}^\infty e^{-\rho t} \frac{[c(t)A(t)]^{1-\theta}}{1-\theta} \frac{L(t)}{H}\, dt \\
 & =\int_{0}^\infty e^{-\rho t} \left[ A(0)^{1-\theta}e^{(1-\theta)gt} \frac{c(t)^{1-\theta}}{1-\theta} \right] \frac{L(0)e^{nt}}{H}  \, dt \\
 & =A(0)^{1-\theta} \frac{L(0)}{H}\int_{0}^\infty e^{-\rho t+(1-\theta)gt+nt} \frac{c(t)^{1-\theta}}{1-\theta}\, dt \\
 & =B\int_{0}^\infty e^{-\beta t} \frac{c(t)^{1-\theta}}{1-\theta} \, dt
\end{align}
$$
其中
$$
\begin{cases}
B & \equiv A(0)^{1-\theta}\frac{L(0)}{H} \\
\beta & \equiv \rho-n-(1-\theta)g
\end{cases}
$$
**注意**：这里我们需要额外假定 $\beta>0$ 避免积分发散。

## 厂商行为

根据竞争性条件有
$$
r=\frac{ \partial F }{ \partial K }=\frac{ \partial ALf(k) }{ \partial k } \frac{ \partial k }{ \partial K }=ALf'(k) \frac{1}{AL} =f'(k)  
$$
以及
$$
\tilde{w}=\frac{ \partial F }{ \partial L }=\frac{ \partial ALf(k) }{ \partial L } =Af(k)+AL\frac{ \partial f(k) }{ \partial k }\frac{ \partial k }{ \partial L }  =Af(k)+ALf'(k)\left( -\frac{K}{AL^{2}} \right)=A[f(k)-kf'(k)]
$$
其中 $w\equiv [f(k)-kf'(k)]$ 为有效劳动收入，即 $\tilde{w}=wA$ 
## 约束条件

有限期界下消费者的终身预算约束（折现到初期）为
$$
\begin{align}
\int_{0}^T e^{-R(t)}\tilde{c}(t) \frac{L(t)}{H}  \, dt+e^{-R(T)}\frac{K(T)}{H}  & = \frac{K(0)}{H}+\int_{0}^T e^{-R(t)}\tilde{w}(t) \frac{L(t)}{H} \, dt \\
\int_{0}^T e^{-R(t)}c(t) \frac{A(t)L(t)}{H}  \, dt  +e^{-R(T)}k(T) \frac{A(T)L(T)}{H}& = k(0)\frac{A(0)L(0)}{H}+\int_{0}^T e^{-R(t)} w(t) \frac{A(t)L(t)}{H} \, dt \\
\end{align}
$$
利用 $A(t)L(t)=A(0)L(0)e^{(n+g)t}$ 以及 $A(T)L(T)=A(0)L(0)e^{(n+g)T}$ 化简可得
$$
\int_{0}^T e^{-R(t)}c(t)e^{(n+g)t} \, dt  +e^{-R(T)+(n+g)T}k(T) = k(0)+\int_{0}^T e^{-R(t)} w(t)e^{(n+g)t}  \, dt 
$$
其中 $R(t)=\int_{0}^t r(\tau)\, d\tau$ 以及 $R(t)=\int_{0}^T r(\tau)\, d\tau$ 为可变利率，若利率不变则 $R(t)=rt$

在无限期界情形时，我们假设家庭财富不会渐进趋于负值，即 no-pongzi-game condition
$$
\lim_{ T \to \infty } e^{-R(T)+(n+g)T}k(T)\geq 0
$$
令 $T\to \infty$ 将预算约束化为不等式形式：
$$
\int_{0}^\infty e^{-R(t)}c(t)e^{(n+g)t} \, dt  \leq k(0)+\int_{0}^\infty e^{-R(t)} w(t)e^{(n+g)t}  \, dt
$$
换言之，一生消费的现值不能超过其初始财富加上一生劳动收入的现值。

移项可得
$$
k(0)+\int_{0}^\infty e^{-R(t)+(n+g)t}[w(t)-c(t)] \, dt\geq 0 
$$
## 模型求解
动态最优化问题为
$$
\begin{split}
\max_{c} &\ U=B\int_{0}^\infty e^{-\beta t}\frac{c(t)^{1-\theta}}{1-\theta} \, dt  \\
\text{s.t.} &\ \beta\equiv\rho-n-(1-\theta)g \\
&\ B\equiv A(0)^{1-\theta}\frac{L(0)}{H} \\
&\ \dot{k}(t)=f(k(t))-c(t)-(n+g+\delta)k(t)
\end{split}
$$
Hamiltonian function is
$$
H(t,k,c,\lambda)\equiv e^{-\beta t}\frac{c(t)^{1-\theta}}{1-\theta}+\lambda(t)[f(k(t))-c(t)-(n+g+\delta)k(t)]
$$
The maximum principle is
$$
\begin{align}
\frac{ \partial H }{ \partial c(t) } & =0 \implies e^{-\beta t}c(t)^{-\theta}=\lambda(t) \tag{1}\\
\frac{ \partial H }{ \partial k(t) } & =-\dot{\lambda}(t)\implies \lambda(t)[f'(k(t))-(n+g+\delta)]=-\dot{\lambda}(t) \tag{2} \\
\frac{ \partial H }{ \partial \lambda(t) } & =\dot{k}(t)
\end{align}
$$
注意 $\frac{ d \ln\lambda(t) }{ d t }=\frac{\dot{\lambda}(t)}{\lambda(t)}$，根据(1)可知
$$
\ln\lambda(t)=-\beta t-\theta \ln c(t)\implies \frac{\dot{\lambda}(t)}{\lambda(t)}=-\beta-\theta\frac{\dot{c}(t)}{c(t)}
$$
代入(2)可得
$$
\frac{\dot{c}(t)}{c(t)}=\frac{f'(k(t))-(n+g+\delta+\beta)}{\theta}=\frac{f'(k(t))-\rho-\theta g-\delta}{\theta}
$$

## 模型动态

两个变量决定两个动态，即 $\dot{c}(c,k)$ 和 $\dot{k}(c,k)$，可以在坐标图中表现出来。

我们记 $\dot{c}=0$ 时 $k=\hat{k}$，根据欧拉方程可知
$$
\begin{cases}
f'(k(t))=\rho+\theta g+\delta & ,\text{if }\dot{c}=0 \text{ and }k=\hat{k} \\
f'(k(t))>\rho+\theta g+\delta & ,\text{if }\dot{c}>0 \text{ and }k<\hat{k}  \\
f'(k(t))<\rho+\theta g+\delta & ,\text{if }\dot{c}<0 \text{ and }k>\hat{k} 
\end{cases}
$$
从第一个式子可以看出 $\dot{c}=0$ 时 $\hat{k}$ 是一个常数 

我们记 $\dot{k}=0$ 时 $c=\hat{c}$，根据资本动态方程 $c(t)=f(k(t))-(n+g+\delta)k(t)-\dot{k}(t)$ 可知
$$
\begin{cases}
c(t)=f(k(t))-(n+g+\delta)k(t) & ,\text{if }\dot{k}=0\text{ and }c=\hat{c}\\
c(t)<f(k(t))-(n+g+\delta)k(t) & ,\text{if }\dot{k}>0\text{ and }c<\hat{c} \\
c(t)>f(k(t))-(n+g+\delta)k(t) & ,\text{if }\dot{k}<0\text{ and }c>\hat{c}
\end{cases}
$$
从第一个式子可以看出 $\dot{k}=0$ 时 $\hat{c}$ 是一个先增后减的曲线，最高点即 $c_{g}$

命题：$\hat{k}<k_{g}$，即稳态资本（$\dot{k}=\dot{c}=0$）一定小于黄金率资本。

证明：根据相位图两条分界线的定义式可知
$$
\begin{cases}
f'(\hat{k}) & =\rho+\theta g+\delta \\
f'(k_{g}) & =n+g+\delta
\end{cases}
$$
根据家庭效用函数积分不发散条件和边际产量递减可知
$$
\rho-n-(1-\theta)g>0\implies f'(\hat{k})>f'(k_{g})\implies \hat{k}<k_{g}
$$

