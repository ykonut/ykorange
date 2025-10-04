---
{"dg-publish":true,"permalink":"/计量经济学/线性CEF模型/","tags":["线性模型"],"created":"2025-01-08T17:09:15.000+08:00","updated":"2025-08-20T16:14:14.863+08:00"}
---

> [!ABSTRACT]
> 根据[[计量经济学/条件期望函数及其性质\|条件期望函数及其性质]]可知，$E[Y\mid X]$ 实现了对 $Y$ 的最小平方预测。因此，除了直接对 $Y$ 建模，还可以转而对 $E[Y\mid X]$ 建模，这里也尝试最简单的线性模型。
## 模型设定

假设 1
$$
Y=E(Y\mid X)+e_{c}
$$
其中 $e_{c}$ 称为 CEF 误差，具有如下性质：
$$
\begin{align*}
E[e_{c}|X]&=0 \tag{1} \\
E[e_{c}]&=0 \tag{2} \\
E[h(X)e_{c}]&=\mathbf{0} \tag{3} \\
Cov[h(X),e_{c}]&=\mathbf{0} \tag{4}
\end{align*}
$$
**Proof**
$$
\begin{align*}
E[e_{c}|X]&=E[Y-E(Y|X)|X]=E[Y|X]-E(Y|X)=0 \tag{1} \\
E[e_{c}]&=E[E(e_{c}|X)]=0 \tag{2} \\
E[h(X)e_{c}]&=E[E(h(X)e_{c}|X)]=E[h(X)E(e_{c}|X)]=\mathbf{0} \tag{3} \\
Cov[h(X),e_{c}]&=E[h(X)e_{c}]-E[h(X)]E[e_{c}]=\mathbf{0} \tag{4}
\end{align*}
$$
假设 2
$$
E(Y|X)=X^{\mathsf{T}}{\beta_{c}}
$$
## 等价形式

假设 2 代入假设 1 可得
$$
Y=X^{\mathsf{T}}\beta_{c}+e_{c}
$$
假设 2 又可推知
$$
\begin{align}
E(Y\mid X)-X^{\mathsf{T}}\beta_{c} & =0 \\
E[Y-X^{\mathsf{T}}{\beta_{c}}\mid X] & =0 \\
E[Y-E(Y\mid X)\mid X] & =0 \\
E[e_{c}\mid X] & =0
\end{align}
$$
因此，所谓线性 CEF 模型
$$
\begin{cases}
Y=E(Y\mid X)+e_{c} \\
E(Y|X)=X^{\mathsf{T}}{\beta_{c}} \\
\end{cases}
$$
其实只是相当于[[计量经济学/线性投影模型\|线性投影模型]]增加一项约束：
$$
\begin{cases}
Y=X^{\mathsf{T}}{\beta_{c}}+e_{c}\\
E(e_{c}|X)=0
\end{cases}
$$