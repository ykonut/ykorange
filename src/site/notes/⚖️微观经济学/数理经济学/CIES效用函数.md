---
{"dg-publish":true,"permalink":"/⚖️微观经济学/数理经济学/CIES效用函数/","tags":["数理经济学"],"created":"2024-10-12T10:24:57.000+08:00","updated":"2024-10-12T10:24:57.000+08:00"}
---

## 定义
考察如下形式的跨期效用函数
$$
U(c_{1},c_{2})=u(c_{1})+\beta u(c_{2})
$$
边际替代率为
$$
\text{MRS}_{1,2}=\frac{\mathrm{d} c_{2}}{\mathrm{d} c_{1}}=-\frac{ \partial U/\partial c_{1} }{ \partial U/\partial c_{2} }
$$
**跨期替代弹性**为
$$
\sigma_{1,2}=\frac{\mathrm{d} \ln\frac{c_{2}}{c_{1}}}{\mathrm{d} \ln \text{MRS}_{1,2}}
$$
特别地，如果 $u(c)$ 为 [[⚖️微观经济学/风险规避系数#CRRA 效用函数\|CRRA 效用函数]] ，即得到常跨期替代弹性（constant intertemporal elasticity of substitution, CIES）效用函数
$$
U(c_{1},c_{2})=\frac{c_{1}^{1-\varepsilon}-1}{1-\varepsilon}+\beta \frac{c_{2}^{1-\varepsilon}-1}{1-\varepsilon}
$$
边际替代率为
$$
\text{MRS}_{1,2}=-\frac{1}{\beta} (\frac{c_{1}}{c_{2}})^{-\varepsilon}
$$
跨期替代弹性为
$$
\sigma=\frac{\mathrm{d} \ln\frac{c_{2}}{c_{1}}}
{\mathrm{d} \left[\ln \left( -\frac{1}{\beta} \right)-\varepsilon \ln \frac{c_{1}}{c_{2}} \right]}
=\frac{\mathrm{d} \ln\frac{c_{2}}{c_{1}}}
{\varepsilon\mathrm{d}  \ln \frac{c_{2}}{c_{1}} }
=\frac{1}{\varepsilon}
$$
可见 CIES 效用函数的跨期替代弹性为 CRRA 效用函数相对风险规避系数的倒数。

## 性质

在所有加法可分的[[⚖️微观经济学/数理经济学/跨期效用函数\|跨期效用函数]]中，属于[[⚖️微观经济学/数理经济学/位似函数\|位似函数]]的有且只有 CIES 效用函数。