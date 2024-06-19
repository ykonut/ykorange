---
{"dg-publish":true,"permalink":"/01 微观经济学/数理经济学/CRS函数/","created":"2023-06-18T16:33:22.143+08:00","updated":"2024-06-19T16:26:04.012+08:00"}
---


定义：若 $f:\mathbb{R}^{n+m}\to\mathbb{R}$ 是自变量 $\mathbf{x}\in \mathbb{R}^n$ 和 $\mathbf{z}\in\mathbb{R}^m$ 的 $1$ 次[[01 微观经济学/数理经济学/齐次函数\|齐次函数]]，满足
$$
f(t\mathbf{x},\mathbf{z})=tf(\mathbf{x},\mathbf{z})\quad \forall t>0
$$
则称 $f$ 是 $\mathbf{x}$ 的 CRS 函数（constant return to scale function），称 $t$ 是 $\mathbf{x}$ 的规模（scale）。

## 边际产出

**命题**：CRS 生产函数的规模不影响边际产出。

**证明**：根据[[01 微观经济学/数理经济学/齐次函数#导数性质\|齐次函数#导数性质]]可知边际产出是0次齐次函数，满足
$$
\frac{\partial f(t\mathbf{x},\mathbf{z})}{\partial x_i}=\frac{\partial f(\mathbf{x},\mathbf{z})}{\partial x_i}
$$
因此，扩大 $t$ 不影响边际产出。

## Wicksell's Law

给定 CRS 生产函数 $y=f(x_{1},x_{2})$，对边际产出 $f_{1}$ 应用欧拉定理
$$
\begin{align}
0\cdot f_{1} & =f_{11}x_{1}+f_{12}x_{2} \\
-f_{11} x_{1} & =f_{12} x_{2}
\end{align}
$$
若假设边际产出 $f_{1}$ 递减（即 $f_{11}<0$），则有 $f_{12}>0$。这意味着 $x_{1}$ 的增加会提高边际产出 $f_{2}$，反之亦然，二者**互补**。这一结果称为 **Wicksell's Law**。

给定 CRS 生产函数 $y=f(x_{1},\dots,x_{n})$，对边际产出 $f_{i}$ 应用欧拉定理
$$
\begin{align}
0\cdot f_{i} & =\sum_{j} f_{ij}x_{j} \\
-f_{ii} x_{i}& =\sum_{j\neq i}f_{ij}x_{j} \\
-f_{ii} \frac{x_{i}}{\sum x} & =\frac{\sum_{j\neq i}f_{ij}x_{j}}{\sum x}
\end{align}
$$
若假设边际产出 $f_{i}$ 递减（即 $f_{ii}<0$），则 $\{ f_{ij} \}_{j\neq i}$ 的加权平均数为正。这意味着 $x_{i}$ 的增加「平均而言」会提高其他要素的边际产出；或者说至少存在一个要素（$\max \{ f_{ij} \}_{j\neq i}$）和 $x_{i}$ **互补**。这一结果可以称为广义 **Wicksell's Law**。

## 替代率递减

**命题**：给定 CRS 生产函数 $y=f(x_{1},x_{2})$，如果所有要素的边际产出都递减，则任意要素对其他要素边际技术替代率的绝对值关于该要素递减。

**证明**：边际技术替代率的导数为
$$
\begin{align}
\frac{\partial \lvert MRTS_{i,j} \rvert}{\partial x_{i}}
 & =\frac{\partial (f_{i}/f_{j})}{\partial x_{i}}  \\
 & = \frac{f_{j}\left( f_{ii}+f_{ij} \frac{\mathrm{d}x_{j}}{\mathrm{d}x_{i}} \right)-f_{i}\left( f_{ji}+f_{jj}\frac{\mathrm{d} x_{j}}{\mathrm{d} x_{i}} \right)}{f_{j}^{2}}   \\
 & = \frac{f_{j}\left( f_{ii}-f_{ij} \frac{f_{i}}{f_{j}}\right)-f_{i}\left( f_{ji}-f_{jj} \frac{f_{i}}{f_{j}}\right)}{f_{j}^{2}}   \\
 & = \frac{f_{j}f_{ii}-f_{ij}f_{i}-f_{i}f_{ij}+f_{jj} \frac{f_{i}^{2}}{f_{j}}}{f_{j}^{2}}   \\
& =\frac{f_{j}^2f_{ii}-2f_{i}f_{j}f_{ij}+f_{i}^{2}f_{jj}}{f_{j }^3}
\end{align}
$$
如果 $f_{ii},f_{jj}<0$，根据 Wicksell's Law 有 $f_{ij}>0$，因此上式为负，证毕。

## 量可分离

**命题**：CRS 生产函数对应的要素需求函数和成本函数是量可分离的，即
$$
\begin{cases}
x_{i}^c(q,\mathbf{w})=qx_{i}^c(1,\mathbf{w}) \\
c(q,\mathbf{w})=qc(1,\mathbf{w})
\end{cases}
$$

**证明**：
将 [[01 微观经济学/成本最小化\|成本最小化]] 的最优解代回F.O.C
$$
\frac{ \partial \mathcal{L} }{ \partial x_{i} }= \sum_{i=1}^nw_ix_i^c(q,\mathbf{w})-\lambda \sum_{i=1}^n\frac{\partial f}{\partial x_i}x_i^c(q,\mathbf{w})=0
$$
根据[[01 微观经济学/成本函数\|成本函数]]的定义
$$
c(q,\mathbf{w})=\sum_{i=1}^nw_ix_i^c(q,\mathbf{w})
$$
根据[[01 微观经济学/包络定理\|包络定理]]有
$$
\frac{\mathrm{d} c(q,\mathbf{w})}{\mathrm{d} q}=\frac{\mathrm{d} \mathcal{L}}{\mathrm{d} q}=\lambda
$$
根据[[01 微观经济学/数理经济学/齐次函数#欧拉定理\|齐次函数#欧拉定理]]有
$$
\sum_{i=1}^n\frac{\partial f}{\partial x_i}x_i^c(q,\mathbf{w})=q
$$
F.O.C.
$$
c(q,\mathbf{w})-\frac{\mathrm{d} c(q,\mathbf{w})}{\mathrm{d} q}q=0
$$
这是一个可分离的微分方程
$$
\begin{align}
\frac{\mathrm{d} c(q,\mathbf{w})}{c(q,\mathbf{w})}&=\frac{\mathrm{d} q}{q} \\
\ln[c(q,\mathbf{w})]&=\ln(q)+C \\
\end{align}
$$
令 $q=1$，解得 $C=\ln[c(1,\mathbf{w})]$，上式取幂可得
$$
\begin{align}
\exp\{\ln[c(q,\mathbf{w})]\}&=\exp\{\ln(q)+\ln[c(1,\mathbf{w})]\} \\
c(q,\mathbf{w})&=qc(1,\mathbf{w}) \\
\sum_{i=1}^nw_ix_i^c(q,\mathbf{w}) & =q\sum_{i=1}^nw_ix_i^c(1,\mathbf{w}) \\
x_{i}^c(q,\mathbf{w}) & =qx_{i}^c(1,\mathbf{w})
\end{align}
$$
证毕。

进一步观察可知
$$
\begin{align*}
AC&\equiv\frac{c(q,\mathbf{w})}{q}=c(1,\mathbf{w}) \\
MC&\equiv\frac{dc(q,\mathbf{w})}{dq}=\frac{dqc(1,\mathbf{w})}{dq}=c(1,\mathbf{w})
\end{align*}
$$
> 直觉：CRS 生产函数暗示了增产的要素组合是不变的，即 $MC=AC$；由于成本函数是累积函数，所以平均成本就等于第一单位的成本。

此外，根据[[01 微观经济学/成本函数#Shephard's lemma\|成本函数#Shephard's lemma]]
$$
\frac{\partial c(1,\mathbf{w})}{\partial w_{i}}=\frac{1}{q}\frac{\partial c(q,\mathbf{w})}{\partial w_{i}}=\frac{x_{i}^c(q,\mathbf{w})}{q}
$$
也就是
$$
\frac{\partial MC}{\partial w_{i}}=\frac{\partial AC}{\partial w_{i}}=\frac{1}{AP_{i}}
$$