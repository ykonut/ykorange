---
{"dg-publish":true,"permalink":"/计量经济学/Population and Sample/"}
---

## 定义

总体（Population）是一组随机变量（Random Variable），可以理解为一种数据生成过程（Data Generating Process）。

在回归分析中，总体一般记作 $(Y,X)$，其中 $Y$ 是一个随机变量，$X$ 是一个随机变量或随机向量。随机向量 $X$ 记作 $X=(X_1,X_2,...,X_k)^T$。

样本（Sample）既可以在理论分析中（事前）看作一组随机变量，也可以在统计分析中（事后）看作一个数据集（Dataset）。

一般地，样本可以记作 $\{(Y_i,X_i):i=1,\cdots,n\}$，其中 $(Y_i,X_i)$ 称为一个观测值（Observation）。随机向量 $X_i$ 记作 $X_{i}=(X_{1i},X_{2i},...,X_{ki})^T$。

常见地，样本可以记作 $(\mathbf{Y},\mathbf{X})$。其中，$\mathbf{Y}=(y_1,y_2,...,y_n)^T$ 是因变量数据向量；$\mathbf{X}$ 是自变量数据向量或数据矩阵。数据矩阵 $\mathbf{X}$ 的每个列分块是一个自变量数据向量，记作 $\mathbf{X}=(\mathbf{X}_1,\mathbf{X}_2,\mathbf{X}_3,...,\mathbf{X}_k)$，其中
$$
\mathbf{X}_j=(x_{1j},x_{2j},\cdots,x_{nj})^T\quad j=1,\cdots,k
$$
> 注意区别，$X_i$ 包含观测值 $i$ 的所有自变量，为 $(k×1)$ 列向量；$\mathbf{X}_j$ 包含自变量 $j$ 的所有观测值，为 $(n×1)$ 列向量。

样本往往被假设为是**独立同分布**的（independent and identically distributed，i.i.d），即如果 $(Y,X)\sim F$ ，则 $(Y_i,X_i)\sim F$ ，且各观测值之间相互独立。

违背独立同分布假设的情形：
- spatial
- time-series
- network
- clustered

## 统计推断

称随机变量 $f(Y,X)$ 为一个总体统计量（statistic）；
称随机变量 $g(Y_{1},\dots,Y_{n},X_{1},\dots,X_{n})$ 为一个样本统计量。

给定一个总体，假定结构方程描述了变量之间的因果关系，因此需要构造总体统计量识别（identificate）结构方程的参数（parameter）；由于总体是不可观测的，需要进一步构造样本统计量推断（infer）总体统计量。

其中，用于识别参数的总体统计量称为 estimand；用于推断总体统计量的样本统计量称为估计量（estimator），再根据数据计算得到估计值（estimate）。
![estimator](https://raw.githubusercontent.com/peco17/picx-images-hosting/master/picgo/image-caf231002acedfdc73616c9960d218b9.jpg)

> “Econometric identification really means just one thing: model parameters or features being uniquely determined from the observable population that generates the data” -Lewbel (2019)

