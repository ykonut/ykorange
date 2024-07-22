---
{"dg-publish":true,"permalink":"/01 微观经济学/数理经济学/CRS函数/","created":"2023-06-18T16:33:22.143+08:00","updated":"2024-07-10T22:47:13.782+08:00"}
---

定义：若 $f:\mathbb{R}^{n+m}\to\mathbb{R}$ 是自变量 $\mathbf{x}\in \mathbb{R}^n$ 和 $\mathbf{y}\in\mathbb{R}^m$ 的函数，满足
$$
f(t\mathbf{x},\mathbf{y})=tf(\mathbf{x},\mathbf{y})\quad \forall t>0
$$
则称 $f$ 关于 $\mathbf{x}$ 是$1$次齐次函数或 CRS 函数（constant return to scale function）。其中，参数 $t$ 称为自变量 $\mathbf{x}$ 的规模（scale）。

## 边际产出

**命题**：CRS 生产函数的生产要素规模不影响边际产出。

**证明**：根据[[01 微观经济学/数理经济学/齐次函数#导数性质\|齐次函数#导数性质]]可知边际产出是$0$次齐次函数，满足
$$
\frac{\partial f(t\mathbf{x},\mathbf{y})}{\partial x_i}=\frac{\partial f(\mathbf{x},\mathbf{y})}{\partial x_i}
$$
因此，扩大 $t$ 不影响边际产出。

## Wicksell's Law

给定 CRS 生产函数 $y=f(x_{1},x_{2})$，对边际产出 $f_{1}$ 应用[[01 微观经济学/数理经济学/齐次函数#欧拉定理\|齐次函数#欧拉定理]]
$$
\begin{align}
0\cdot f_{1} & =f_{11}x_{1}+f_{12}x_{2} \\
-f_{11} & =f_{12} \frac{x_{2}}{x_{1}}
\end{align}
$$
若边际产出 $f_{1}$ 递减（即 $f_{11}<0$），则有 $f_{12}>0$。这意味着 $x_{1}$ 的增加会提高边际产出 $f_{2}$，反之亦然，二者**互补**。这一结果称为 **Wicksell's Law**。

给定 CRS 生产函数 $y=f(x_{1},\dots,x_{n})$，对边际产出 $f_{i}$ 应用欧拉定理
$$
\begin{align}
0\cdot f_{i} & =\sum_{j} f_{ij}x_{j} \\
-f_{ii} x_{i}& =\sum_{j\neq i}f_{ij}x_{j} \\
-f_{ii} & =\sum_{j\neq i}f_{ji} \frac{x_{j}}{x_{i}}
\end{align}
$$
若边际产出 $f_{i}$ 递减（即 $f_{ii}<0$），则 $\{ f_{ji} \}_{j\neq i}$ 的加权和为正。这意味着 $x_{i}$ 的增加「平均而言」会提高边际产出 $\{ f_{j} \}_{j\neq i}$，或者至少存在一个 $x_{j}$ 和 $x_{i}$ **互补**（$\max \{ f_{ij} \}_{j\neq i}>0$）。这一结果可以称为广义 **Wicksell's Law**。

## 二元生产性质

这部分性质仅适用于二元生产函数。
### 边际产出同调

给定 CRS 生产函数 $y=f(x_{1},x_{2})$，分别对边际产出 $f_{1}$ 和 $f_{2}$ 应用[[01 微观经济学/数理经济学/齐次函数#欧拉定理\|齐次函数#欧拉定理]]
$$
\begin{cases}
-f_{11}x_{1}=f_{12}x_{2} \\
-f_{22}x_{2}=f_{21}x_{1}
\end{cases}\implies x_{1}x_{2}f_{11}f_{22}=x_{1}x_{2}(f_{12})^{2}\implies  x_{1}x_{2}[f_{11}f_{22}-(f_{12})^{2}]=0
$$
若 $x_{1}x_{2}\neq 0$，则
$$
g(x_{1},x_{2})\equiv f_{11}f_{22}-(f_{12})^{2}=0
$$
若 $x_{1}x_{2}=0$，只要生产函数 $y$ 二阶连续可微，则
$$
g(x_{1},x_{2})\equiv f_{11}f_{22}-(f_{12})^{2}=0
$$
否则 $g(0,0)$ 将成为可去间断点，与连续性矛盾。

综上所述
$$
f_{11}f_{22}=(f_{12})^{2}\geq 0
$$
即边际产出 $f_{1}$ 和 $f_{2}$ **单调性相同**。因此，对于二元 CRS 生产函数而言，任意一个要素边际产出递减就意味着另一个要素边际产出递减。
### 替代率递减

**命题**：给定 CRS 生产函数 $y=f(x_{1},x_{2})$，如果所有要素的边际产出都（严格）递减，则任意要素对其他要素边际技术替代率的绝对值关于该要素（严格）递减。

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

注意到 $y=f(x_{1},x_{2})$ 的加边 Hessian 矩阵（Bordered Hessian）为
$$
B=
\begin{bmatrix}
0 & f_{1} & f_{2} \\
f_{1} & f_{11} & f_{12} \\
f_{2} & f_{21} & f_{22}
\end{bmatrix}
$$
如果 $y$ 为拟凹函数，则
$$
\begin{align}
\lvert B_{1} \rvert & =0\cdot f_{11}-(f_{1})^{2}\leq 0 \\
\lvert B_{2} \rvert & =2f_{1}f_{2}f_{12}-(f_{1})^{2}f_{22}-(f_{2})^{2}f_{11}\geq 0
\end{align}
$$
其中
$$
\lvert B_{2} \rvert\geq 0 \iff \frac{\partial \lvert MRTS_{i,j} \rvert}{\partial x_{i}}\geq 0
$$
因此，获得边际替代率递减的二元生产函数有两种方式：
1. 假设生产函数为CRS 函数，边际产出递减（$f_{ii},f_{jj}\leq0$）
2. 假设生产函数为拟凹函数。
## 齐次生产性质

根据[[01 微观经济学/数理经济学/齐次函数#齐次生产性质\|齐次函数#齐次生产性质]]可知，CRS 生产函数意味着
$$
\begin{align}
c(\mathbf{w},q)  & =qc(\mathbf{w},1) \\
x_{i}^C(\mathbf{w},q) & =qx_{i}^C(\mathbf{w},1)
\end{align}
$$
特别地，对于 CRS 生产函数而言
$$
\begin{align*}
AC&\equiv\frac{c(\mathbf{w},q)}{q}=c(\mathbf{w},1) \\
MC&\equiv\frac{\mathrm{d}c(\mathbf{w},q)}{\mathrm{d}q}=c(\mathbf{w},1)
\end{align*}
$$
> 直觉：CRS 生产函数暗示了增产的要素组合是不变的，即 $MC=AC$；由于成本函数是累积函数，所以平均成本就等于第一单位的成本。

此外，根据[[01 微观经济学/成本函数#Shephard's lemma\|成本函数#Shephard's lemma]]
$$
\frac{\partial c(\mathbf{w},1)}{\partial w_{i}}=x_{i}^C(\mathbf{w},1)=\frac{x_{i}^C(\mathbf{w},q)}{q}
$$
也即
$$
\frac{\partial MC}{\partial w_{i}}=\frac{\partial AC}{\partial w_{i}}=\frac{1}{AP_{i}}
$$