---
{"dg-publish":true,"permalink":"/02 宏观经济学/Solow Model/","created":"2024-02-27T20:15:03.943+08:00","updated":"2024-06-18T18:17:33.519+08:00"}
---


缺乏家庭最优决策是索洛模型和新古典增长模型的主要区别。
## 假设

### 生产函数的形式
1. 劳动增强型（labor-augumenting/Harrod-neutral) ：$Y=F(K,AL)$
2. 资本增强型（capital-augumenting）：$Y=F(AK,L)$
3. 平衡增强型（Hicks-neutral）： $Y=AF(K,L)$
> [[01 微观经济学/数理经济学/Cobb-Douglas函数\|Cobb-Douglas函数]] 的同时符合上述三种形式往往有解。 

### 生产函数的特征

①规模报酬不变
   $$F(cK,cAL)=cF(K,AL)\quad \forall c\geq 0$$
用途是将总量生产函数转化为个量生产函数
   $$\frac{Y}{AL}=F\left( \frac{K}{AL},1 \right)\leftrightarrow  y=f(k)$$
②边际产量为正且递减
   $$f(0)=0 \quad f'(k)>0 \quad f''(k)<0$$
③稻田条件（Inada condition）
   $$\lim_{ k \to 0 }f'(k)=\infty \quad \lim_{ k \to \infty }f'(k)=0$$
### 投入增速

假设劳动和知识匀速增长
$$
\dot{L}(t)=nL(t) \quad \dot{A}(t)=gA(t)
$$
> [!NOTE]
> 命题： $$\frac{\dot{X}(t)}{X(t)}=g \leftrightarrow X(t)=e^{gt}X(0)$$
> 证明： $$\frac{\dot{X}(t)}{X(t)}=\frac{\mathrm{d}X(t)/X(t)}{\mathrm{d}t}=\frac{\mathrm{d}\ln X(t)}{\mathrm{d}t}=g \implies \ln X(t)=gt+C$$
> 令 $t=0$，解得 $C=\ln X(0)$，即 $\ln X(t)=gt+\ln X(0)$，取幂得 $X(t)=e^{gt}X(0)$
> 
> **由此可见，需要 $\dot{X}$ 时可以先找 $\ln X$**

总量资本的动态方程为
$$
\begin{align}
\dot{K}(t) & \equiv I(t)-\delta K(t) \\
 & =[Y(t)-C(t)]-\delta K(t) \\
 & =sY(t)-\delta K(t)
\end{align}
$$
## 动态

为了找到劳均资本 $\dot{k}$ 的动态方程，可以先找 $\ln k$
$$
\begin{align}
k & =\frac{K}{AL} \\
\ln k & =\ln K-\ln A-\ln L \\
\frac{\mathrm{\mathrm{d}} \ln k}{\mathrm{\mathrm{d}}t} & =\frac{\mathrm{\mathrm{d}} \ln K}{\mathrm{\mathrm{d}}t}- \frac{\mathrm{\mathrm{d}} A}{\mathrm{\mathrm{d}} t}-\frac{\mathrm{\mathrm{d}} L}{\mathrm{\mathrm{d}} t} \\
\frac{\dot{k}}{k} & =\frac{\dot{K}}{K}-\frac{\dot{A}}{A}-\frac{\dot{L}}{L}  \\
\frac{\dot{k}}{k} & =\frac{\dot{K}}{K}-g-n \\ 
\end{align}
$$
其中
$$
\begin{align}
\frac{\dot{K}}{K} & =\frac{Y-C-\delta K}{K}=\frac{Y}{K}-\frac{C}{K}-\delta=\frac{f(k)}{k}-\frac{c}{k}-\delta\\
& =\frac{sY-\delta K}{K}=s\frac{Y}{K}-\delta=s\frac{f(k)}{k}-\delta
\end{align}
$$
从而得到劳均资本的动态方程：
$$
\begin{align}
\dot{k} & =f(k)-c-(n+g+\delta)k \\
 & =sf(k)-(n+g+\delta)k
\end{align}
$$
其中：
-  $sf(k)$ 称为实际投资（actual investment）；
- $(n+g+\delta)k$ 称为持平投资（breakeven investment）。

> [!NOTE]
> 由劳均资本的动态方程可以直接得到劳均资本增长率的表达式：
> $$
> g_{k}\equiv\frac{\dot{k}}{k}=\frac{s f(k)}{k}-(n+g+\delta)
> $$
> 根据稻田条件可知
> $$
> \lim_{ k \to 0 } \frac{f(k)}{k}=\infty \quad \lim_{ k \to \infty } \frac{f(k)}{k}=0
> $$
> 结合零点定理和边际产出递减可知，函数 $g_{k}(k)$ 必定存在唯一零点，即稳态。
> 
> 因此，[[02 宏观经济学/内生增长模型\|内生增长模型]]往往通过放松稻田条件和边际产出递减假设避免稳态。

## 稳态

当 $g_{k}=0$ 即 $\dot{k}=0$ 时称为**稳态**，将稳态劳均资本 $k^*$ 代入动态方程可得稳态方程
$$
sf(k^*)=(n+g+\delta)k^*
$$
这意味着均衡的**储蓄率为常数**
$$
s^*=\frac{(n+g+\delta)k^*}{f(k^*)}
$$稳态时总量资本增长率为 $n+g$
$$
\frac{\dot{k}}{k}=\frac{\dot{K}}{K}-\frac{\dot{A}}{A}-\frac{\dot{L}}{L}=0 \implies \frac{\dot{K}}{K}=n+g
$$
稳态时经济增长率为 $n+g$
$$
\frac{\dot{Y}}{Y}=\frac{\mathrm{d}\ln Y}{\mathrm{d}t}=\frac{\mathrm{d}\ln (ALf(k))}{\mathrm{d}t}=\frac{\mathrm{d}\ln A}{\mathrm{d}t}+\frac{\ln L}{\mathrm{d}t}+\frac{\mathrm{d}\ln f(k)}{\mathrm{d}k} \frac{\mathrm{d}k}{\mathrm{d}t}=n+g
$$
人均资本增长率
$$
\frac{\dot{K/L}}{K/L}=\frac{\mathrm{d}\ln K/L}{\mathrm{d}t}=\frac{\mathrm{d}\ln K}{\mathrm{d}t}-\frac{\mathrm{d}\ln L}{\mathrm{d}t}=g
$$
由此可见，所谓的稳态就是**匀速增长**。
## 比较静态分析

接下来分析参数如何影响稳态，稳态条件的几何分析是一种直观方法。
![image.png](https://raw.githubusercontent.com/ykonut/picx-images-hosting/master/picgo/image-556a64421dfb625707d50d45436aff68.png)
其中，参数 $s$ 的分析最有意义，因为储蓄率比较容易干预，下面进行代数分析。

根据稳态条件，稳态解 $k^*$ 可以看作四个参数的隐函数，即 $k^*=k^*(s,n,g,\delta)$

定义函数
$$
G=(n+g+\delta)k^*-sf(k^*)
$$
根据隐函数定理有
$$
\frac{\partial k^*}{\partial s}=- \frac{\partial G/\partial s}{\partial G/\partial k^*}=\frac{f(k^*)}{(n+g+\delta)-f'(k^*)}
$$
我们更关心参数对 GDP 的影响，可以使用链式法则求解
$$
\frac{ \partial y^* }{ \partial s }=\frac{ \partial f(k^*) }{ \partial k^* }\frac{ \partial k^* }{ \partial s }=\frac{f'(k^*)f(k^*)}{(n+g+\delta)-sf'(k^*)}
$$
导数的经济意义仍不甚清楚，所以尝试进一步构造为**弹性**
$$
\frac{ \partial y^* }{ \partial s } \frac{s}{y^*} =\frac{f'(k^*)}{\frac{n+g+\delta}{s}-f'(k^*)}=\frac{f'(k^*)}{\frac{f(k^*)}{k^*}-f'(k^*)}=\frac{k^*f'(k^*)}{f(k^*)-k^*f'(k)}=\frac{\alpha_{k}}{1-\alpha_{k}}
$$
其中 $\alpha_{k}=\frac{k^*f'(k^*)}{f(k^*)}$ 可以看作归属劳均资本的产出份额。

为什么？根据[[01 微观经济学/数理经济学/齐次函数#欧拉定理\|齐次函数#欧拉定理]]
$$
\begin{align}
F(K,AL) & =K\frac{ \partial F }{ \partial K }+AL\frac{ \partial F }{ \partial AL }  \\
f(k) & = k\frac{ \partial F }{ \partial K }+\frac{ \partial F }{ \partial AL }  
\end{align}
$$
其中 $\frac{ \partial F }{ \partial K }=\frac{ \partial ALf(k) }{ \partial k }\frac{ \partial k }{ \partial K }=ALf'(k) \frac{1}{AL}=f'(k)$，因此
$$
f(k)=kf'(k)+\frac{ \partial F }{ \partial AL } 
$$
所以 $\frac{kf'(k)}{f(k)}$ 可以看作归属劳均资本的份额。

## 黄金率

我们仅仅知道储蓄率越高稳态就越高，但是并不能说哪一个稳态更好，黄金率即人为规定了消费最高的稳态是最好的稳态，即 $c^*_{g}\equiv\max c^*$

根据稳态消费的定义结合稳态条件
$$
c^*=f(k^*)-sf(k^*)=f(k^*)-(n+g+\delta)k^*
$$
F.O.C.
$$
\frac{ d c^*(k^*) }{ d k^* }=f'(k^*)-(n+g+\delta)=0 
$$
这个式子可以解得 $k^*_{g}$，代回目标函数即可得到 $c^*_{g}$；这个式子还表明 $k^*_{g}$ 的几何意义，是持平投资线的平行线和曲线 $f(k)$ 的切点。 

由 $k^*_{g}$ 可以反推出一个 $s_{g}$，我们称 $s>s_{g}$ 的范围为**动态无效率区间**，这是因为降低 $s$ 无论在短期和长期都可以带来帕累托改进：在短期消费水平提高，在长期稳态消费水平提高。

## 收敛速度

泰勒公式
$$
f(x) = f(x_{0}) + f'(x_{0})(x-x_{0}) + f''(x_{0}) \frac{(x-x_{0})^{2}}{2!} + \dots +f^{(n)}(x_{0})\frac{(x-x_{0})^n}{n!}+R_{n}
$$
我们对动态方程 $\dot{k}(k)$ 在 $k^*$ 处进行一阶泰勒展开
$$
\dot{k}(k)\approx \dot{k}(k^*)+\left.\frac{ \partial \dot{k} }{ \partial k } \right|_{k=k^*}(k-k^*)
$$
其中 $\dot{k}(k^*)=0$，记 $\frac{ \partial \dot{k} }{ \partial k }=\lambda$ 可得
$$
\dot{k}(t)\approx \lambda k-\lambda k^*
$$
套用 [[02 宏观经济学/常微分方程\|常微分方程]] 通解公式
$$
\begin{align}
k(t)&\approx Ae^{\lambda t}+e^{\lambda t}\int e^{-\lambda t}(-\lambda k^*) \, dt  \\
&\approx Ae^{\lambda t}+e^{\lambda t}(e^{-\lambda t}k^*+B) \\
&\approx Ce^{\lambda t}+k^* \\
&\approx [k(0)-k^*]e^{\lambda t}+k^* 
\end{align}
$$
其中，令 $t=0$ 可得 $C=k(0)-k^*$


> [!NOTE]
> 或者换一种观点$$\dot{k}(t)\approx \lambda (k-k^*)$$
> 即资本减去一个常数后按固定速率增长 $k(t)-k^*\approx [k(0)-k^*]e^{\lambda t}$

现在来计算 $\lambda$
$$
\begin{align}
\left.\frac{ \partial \dot{k} }{ \partial k } \right|_{k=k^*} & =\left.\frac{ \partial [sf(k)-(n+g+\delta)k] }{ \partial k } \right|_{k=k^*} \\
 & =sf'(k^*)-(n+g+\delta) \\
 & =\frac{(n+g+\delta)k^*}{f(k^*)} f'(k^*)-(n+g+\delta) \\
 & =(n+g+\delta)\left[ \frac{f'(k)k^*}{f(k^*)}-1 \right] \\
 & =(n+g+\delta)(\alpha_{k}-1)
\end{align}
$$

例题：若 $\alpha_{k}$ 为 $\frac{1}{3}$，$n+g+\delta$ 为 6%，则多久可以收敛一半？

解答：$\lambda=-0.04$，这里相当于问
$$
\begin{align}
\frac{1}{2}[k(0)-k^*] & \approx [k(0)-k^*]e^{\lambda t} \\
\frac{1}{2} & \approx e^{\lambda t} \\
\end{align}

$$
解得 $t\approx\frac{\ln 2}{0.04}\approx 17.3$

---
Q: 新古典生产函数的三个假设是什么？
A: ①规模报酬不变
   $$F(cK,cAL)=cF(K,AL)\quad \forall c\geq 0$$
②新古典生产
   $$f(0)=0 \quad f'(k)>0 \quad f''(k)<0$$
③稻田条件（Inada condition）
   $$\lim_{ k \to 0 }f'(k)=\infty \quad \lim_{ k \to \infty }f'(k)=0$$
<!--ID: 1717234008152-->



Q: Solow Model 中劳均资本的动态方程？
A: $$
\dot{k}=sf(k)-(n+g+\delta)k
$$
<!--ID: 1717233375940-->


Q: Solow Model 中稳态产出 $y^*$ 关于储蓄率 $s$ 的弹性？
A: $$
\frac{ \partial y^* }{ \partial s } \frac{s}{y^*} =\frac{\alpha_{k}}{1-\alpha_{k}}
$$
其中 $\alpha_{k}=\frac{k^* f'(k^*)}{f(k^*)}$ 可以看作归属劳均资本的产出份额。
<!--ID: 1717234008171-->



Q: Solow Model 中稳态的黄金率水平是如何定义的？
A: 最大化消费的稳态称为黄金率水平。
根据稳态消费的定义结合稳态条件
$$
c^*=f(k^*)-sf(k^*)=f(k^*)-(n+g+\delta)k^*
$$
F.O.C.为$f'(k^*)=(n+g+\delta)=0$
<!--ID: 1717234008180-->



Q: Solow Model 中收敛速度指的是什么，通常用什么符号表示？
A: 收敛速度指 $\dot{k}$ 动态方程一阶泰勒展开中的一阶导数
$$
\dot{k}(k)\approx \dot{k}(k^*)+\left.\frac{ \partial \dot{k} }{ \partial k } \right|_{k=k^*}(k-k^*)
$$
通常记作 $\left.\frac{ \partial \dot{k} }{ \partial k } \right|_{k=k^*}=\lambda$ 
<!--ID: 1717233316435-->


Q: Solow Model 中收敛速度的表达式？
A: $$
\lambda=(n+g+\delta)(\alpha_{k}-1)
$$
<!--ID: 1717233385719-->


