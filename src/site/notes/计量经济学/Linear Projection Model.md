---
{"dg-publish":true,"permalink":"/计量经济学/Linear Projection Model/","tags":["线性模型"],"created":"2025-01-05T17:06:23.000+08:00","updated":"2025-08-20T16:14:14.866+08:00"}
---

> [!ABSTRACT]
> 由于 CEF 的函数形式本质上是未知的，[[计量经济学/线性CEF模型\|线性CEF模型]] 实际上使用了很强的假设（上帝视角），且没有给出参数估计量。为了假设更为稳健，改为无论真实的 CEF 是什么，都进行线性拟合（符合实践）并给出参数估计量，为了使得参数估计量存在添加了一些技术性假设。
## Setup

Linear CEF Model 设定如下：
1. 定义 Linear Projection Error；
2. 不对 CEF 形式作出假设；
3. 保证模型参数可识别。
$$
e_{p}\equiv Y-X^{\mathsf{T}}{\beta}_{p}\tag{1}
$$
其中，${\beta}_{p}$ 定义为
$$
{\beta}_{p}\equiv \mathop{\arg\min}\limits_{b\in \mathbb{R}^k}E[(Y-X^{\mathsf{T}}b)^2]
$$
为了保证 ${\beta}_{p}$ 有解，假设 $Y$ 和 $X$ 具有有限的期望、方差和协方差：
$$
\begin{cases}
E(Y^2)<\infty  \\
E(\|X\|^{2} )<\infty  \\
E(XX^{\mathsf{T}}) \text{ is positive definite.} \\
\end{cases}
\tag{2}
$$
## 求解参数

根据 $\beta_{p}$ 的定义，设 $S(b)\equiv E[(Y-X^{\mathsf{T}}b)^2]$ ，展开为
$$
S(b)=E[(Y^{\mathsf{T}}-b^{\mathsf{T}}X)(Y-X^{\mathsf{T}}b)]=E[Y^2]-2b^{\mathsf{T}}E[XY]+b^{\mathsf{T}}E[XX^{\mathsf{T}}]b
$$
F.O.C（根据[[计量经济学/矩阵求导\|矩阵求导]]）
$$
\frac{\partial S(b)}{\partial b}=-2E[XY]+2E[XX^{\mathsf{T}}]b=0\implies {\beta}_{p}\equiv E(XX^{\mathsf{T}})^{-1}E(XY)
$$
> [!NOTE]
> 值得注意的是，根据 [[计量经济学/条件期望函数及其性质#Law of Iterated Expectations\|期望迭代法则]] 有
> $$
> \beta_{p}=E(XX^{\mathsf{T}})^{-1}E(XE[Y\mid X])
> $$
> 因此 $Y$ 对 $X$ 的投影参数和 $E[Y\mid X]$ 对 $X$ 的投影参数是一致的。

## LP Error
$$
\begin{align*}
E[Xe_p]&=\mathbf{0} \tag{1} \\
E[e_{p}]&=0 \tag{2} \\
Cov[X_{j},e_{p}]&=0\quad j=1,\ldots,k \tag{3}
\end{align*}
$$
**Proof**
$$
\begin{align*}
E[Xe_{p}]
&=E[X(Y-X^{T}{\beta})] \\
&=E[XY]-E[XX^{\mathsf{T}}]{\beta}\\
&=E[XY]-E[XX^{\mathsf{T}}]E[XX^{\mathsf{T}}]^{-1}E[XY]\\
&=\mathbf{0}
\end{align*}\tag{1}
$$
> [!IMPORTANT]
> $(2)$ 和 $(3)$ 的证明都要求 $X$ 包含常数项。

$(1)$ 表明 $E[(X_{1}e_{p},\ldots,X_{k}e_{p})^{\mathsf{T}}]=\mathbf{0}$，若 $X$ 包含常数项，则对应的分量有
$$
E[e_{p}]=0 \tag{2}
$$
根据 $(1)$ 和 $(2)$ 可知
$$
Cov[X_{j},e_{p}]=E[X_{j}e_{p}]-E[X_{j}]E[e_{p}]=0 \tag{3}
$$
## Best Linear Predictor

**Theorem**
$$
{\beta}_{p}= \mathop{\arg\min}\limits_{b\in \mathbb{R}^k}E\{(E[Y\mid X]-X^{\mathsf{T}}b)^2\}
$$
**Proof**
According to the definition of ${\beta}$
$$
\begin{align}
E[(Y-X^{\mathsf{T}}b)^2]
&=E[(Y-E[Y\mid X]+E[Y\mid X]-X^{\mathsf{T}}b)^2] \\
&=E[(Y-E[Y\mid X])^2]+E[(E[Y\mid X]-X^{\mathsf{T}}b)^2]+ \\
&+2E[(Y-E[Y\mid X])(E[Y\mid X]-X^{\mathsf{T}}b)]
\end{align}
$$
first term
$$
E[(Y-E[Y\mid X])^2]=E[e^2]\ge0
$$
last term (with $E(h(X)e)=0$)
$$
2E\{(Y-E[Y\mid X])(E[Y\mid X]-X^{\mathsf{T}}b)\}=2E\{e(E[Y\mid X]-X^{\mathsf{T}}b)\}=0
$$
因此，${\beta}_{p}$ 的定义等价于对第二项求解最小值，命题得证。

> [!SUMMARY]
> 1. 条件期望函数是 $Y$ 的**最优估计**（根据 [[计量经济学/条件期望函数及其性质#Best Predictor\|CEF的性质]]）
> 2. 线性投影是 $Y$ 的**最优线性估计**（根据 ${\beta}_{p}$ 的定义）
> 3. 线性投影是条件期望函数的**最优线性估计**（根据上述 Theorem）
> 
>虽然简单的线性投影对 $Y$ 的预测效果十分糟糕，但计量经济学更关心 $E[Y\mid X]$ 的变化规律。在 $X$ 为离散变量且模型饱和时（包含所有交互项），线性投影甚至能完全拟合条件期望函数 $E[Y\mid X]$，因此线性投影仍是一个实用的技术。
