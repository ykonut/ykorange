---
{"dg-publish":true,"permalink":"/CS/计算机语言/R基础笔记/","created":"2025-11-02 15:25","updated":"2025-11-10 17:26"}
---


# 获取帮助

```R
# 帮助文档
?solve
help(solve)

# 搜索文档
??"[["
help.search("[[")

# 在线文档
help.start()

# 运行文档中的例子
example(solve)
```

# 命令行


```zsh
R  # 进入R环境
source("script.r") #执行R脚本
system("ls") #执行shell命令
q() # 退出R环境
```

输出展示和保存
```R
( x<-1:10 ) # 加括号可以在赋值的同时也打印结果
dput(x) # 打印对象的纯文本表示

sink("log.txt") # 开始记录输出日志（同时展示输出）
sink() #保存日志
```

# 对象

## 类型查询

R 总共有 4 个类型查询函数，分别是：

- `class()`
- `typeof()`
- `mode()`
- `storage.mode()`
它们之间的区别十分繁琐，大多数时候使用 `class()` 即可。

有人整理了它们所有可能的返回值及其对应关系（[参考链接](https://stackoverflow.com/questions/8855589/a-comprehensive-survey-of-the-types-of-things-in-r-mode-and-class-and-type)）：

| spoken type         | class       | typeof      | mode        | storage.mode |
| :------------------ | :---------- | :---------- | :---------- | :----------- |
| logical vector      | logical     | logical     | logical     | logical      |
| integer vector      | integer     | integer     | numeric     | integer      |
| numeric vector      | numeric     | double      | numeric     | double       |
| complex vector      | complex     | complex     | complex     | complex      |
| character vector    | character   | character   | character   | character    |
| raw vector          | raw         | raw         | raw         | raw          |
| factor              | factor      | integer     | numeric     | integer      |
| logical matrix      | matrix      | logical     | logical     | logical      |
| logical matrix      | array       | logical     | logical     | logical      |
| numeric matrix      | matrix      | double      | numeric     | double       |
| numeric matrix      | array       | double      | numeric     | double       |
| logical array       | array       | logical     | logical     | logical      |
| numeric array       | array       | double      | numeric     | double       |
| list                | list        | list        | list        | list         |
| pairlist            | pairlist    | pairlist    | pairlist    | pairlist     |
| data frame          | data.frame  | list        | list        | list         |
| closure function    | function    | closure     | function    | function     |
| builtin function    | function    | builtin     | function    | function     |
| special function    | function    | special     | function    | function     |
| environment         | environment | environment | environment | environment  |
| null                | NULL        | NULL        | NULL        | NULL         |
| formula             | formula     | language    | call        | language     |
| expression          | expression  | expression  | expression  | expression   |
| call                | call        | language    | call        | language     |
| name                | name        | symbol      | name        | symbol       |
| paren in expression | (           | language    | (           | language     |
| brace in expression | {           | language    | call        | language     |
| S3 lm object        | lm          | list        | list        | list         |
| S4 dummy object     | dummy       | S4          | S4          | S4           |
| external pointer    | externalptr | externalptr | externalptr | externalptr  |

## 类型判断

R 有一系列 `is` 开头的类型判断函数。

- 数据类型
	- `is.numeric(x)`：是否为数值型（包括整数和双精度）。
		- `is.integer(x)`：是否为整数型。
		- `is.double(x)`：是否为双精度浮点数。
	- `is.character(x)`：是否为字符型。
	- `is.logical(x)`：是否为逻辑型（TRUE/FALSE）。
	- `is.complex(x)`：是否为复数型。
	- `is.raw(x)`：是否为原始字节。
- 数据结构
	- `is.vector(x)`：是否为向量（原子向量或 list，且没有除 names 外的属性）。⚠️ 很严格，很多带属性的对象会返回 FALSE。
		- `is.atomic(x)`：是否为原子向量（数值、字符、逻辑等，不包括 list）。
		- `is.list(x)`：是否为列表。
	- `is.matrix(x)`：是否为矩阵。
	- `is.array(x)`：是否为数组。
	- `is.data.frame(x)`：是否为数据框。
	- `is.factor(x)`：是否为因子。
- 特殊数值
	- `is.na(x)`：是否为缺失值 NA (Not Available)。
	- `is.nan(x)`：是否为非数值 NaN (Not a Number)，是 NA 的子集。
	- `is.finite(x)`：是否为有限数值。
	- `is.infinite(x)`：是否为 ±Inf。
- 对象系统
	- `is.object(x)`：是否为对象（即有类属性）。
	- `is.function(x)`：是否为函数。
	- `is.environment(x)`：是否为环境。

## 列表

```R
alist<-list(a = 10, b = 20, c = 30)
# 判断对象是否属于列表
is.list(alist)
#返回第一元素子列（list）
alist[1]
alist["a"]

#返回第一元素的值（vector）
alist[[1\|1]]
alist[["a"]]
alist$a

#返回若干元素子列
alist[1:2]
alist[c("a","c")]

#返回若干元素的值
unname(unlist(alist[c("a", "c")]))
unname(sapply(alist[c("a", "c")], identity))
```

难点：子列和数值不同

使用 unname(list[1]) 得到的结果和 list [[1\|1]] 完全一致？

不完全一样。

简要说明：list[1] 返回一个长度为 1 的子列表（仍是 list）；list[[1\|1]] 返回第 1 个元素本身（元素的类型可能是向量、data.frame、list 等）。unname() 去掉的是对象的 names 属性：对 list[1] 去名后仍是一个长度 1 的 list；对 list[[1]] 去名则是去掉该元素的名字（如果它有名字）。

```R
# R
lst <list(a = 1:3, b = 4)

lst[1]
# -> list(a = 1:3)

unname(lst[1])
# -> list(1:3)      # 仍是一个 list（只是没有名字）

lst[[1]]
# -> 1 2 3          # 直接是数值向量

identical(unname(lst[1]), lst[[1]])
# -> FALSE

# 若要比较子列表中实际元素与提取元素是否相同：
identical(unname(lst[1])[[1]], lst[[1]])
# -> TRUE

# 若想得到没有名字的元素，使用 unname(lst[[1]])
unname(lst[[1]])
```

## 数据框

- 使用 `names(data)` 返回数据可用变量名
	- 通过 `names$var` 返回指定变量
- 使用 `colnames(data)` 得到的结果是一样的
- 几乎不用 `rownames(data)`，因为返回的只是 ID

提取变量的三种方法

```R
# 方法一：逐个提取
data$var1
data$var2
# 方法二：将所有变量加入命名空间
attach(data)
var1
var2
detach(data)
# 方法三：临时加入命名空间
with(data,plot(var1,var2))
```

## 模型

使用 `names(model)` 返回模型对象所有可用属性名称向量。

要访问某个指定属性，可以

- 通过 `model$atrr`
- 通过特定函数
其中，比较常用的几个如下表所示：

| 名称            | 函数                            | 含义     |
| ------------- | ----------------------------- | ------ |
| coefficients  | `coef()`, `coefficients()`    | 回归系数向量 |
| residuals     | `resid()`, `residuals()`      | 残差向量   |
| fitted.values | `fitted()`, `fitted.values()` | 拟合值向量  |

此外，可以

- 使用 `summary(model)` 返回回归表格
- 使用 `nobs(model)` 返回观测值数量
- 使用 `coef(model)["var1"]` 或 `coef(model)[1]` 返回回归系数向量**切片**
- 使用 `coef(model)[["var1"]]` 或 `coef(model)[[1]]` 返回回归系数向量**切片的值**

其他可用变量如下表所示：

| 名称          | 含义                               |
| ----------- | -------------------------------- |
| effects     | 来自设计矩阵 QR 分解的正交化“效应”向量（内部计算用）    |
| rank        | 设计矩阵的秩（矩阵列线性无关的个数）               |
| assign      | 将系数向量的元素映射到模型项的整数向量              |
| qr          | QR 分解的列表（包含 R 矩阵、pivot 等，用于求解系数） |
| df.residual | 残差自由度（n - rank）                  |
| xlevels     | 因子变量在拟合时的水平列表（每个因子的水平）           |
| call        | 拟合模型时的函数调用（match.call() 的结果）     |
| terms       | terms 对象（表示模型公式和变量信息）            |
| model       | 用于拟合的 model.frame（包含响应和自变量原始数据）  |

## 对象存取

```R
#===纯文本格式===
dput(df,file="df.R")   #保存单个对象/返回原始格式
new.df<-dget("df.R")   #读取单个对象
dput(names(df))        #用例：返回df的变量名向量

dump(c("df1", "df2"), file = "data.R")  # 保存多个对象
source("data.R")                        # 读取多个对象

#===二进制格式===
save(df, file = "df.rda")         # 保存单个对象
save.image(file = "all.RData")    # 保存所有对象
load("df.rda")                    # 加载单个对象
load("all.RData")                 # 加载所有对象
# .rda和.RData 是完全相同的格式

```

# 环境管理

一切对象都存在于环境中。环境可看作对象名到对象映射的集合，每个环境都有一个父环境环环相扣，R 会沿着环境链条逐级查找对象。

搜索路径（Search Path）展示了部分环境链，包括：

- 存放工作对象的 `.GlobalEnv` 环境
- 当前已加载的数据框环境和包环境

```R
search() #列出当前搜索路径

library(ggplot2) #将包环境加入搜索路径（不加参数则展示所有已安装的包）
detach("package:ggplot2") #从搜索路径移除包环境
renv::init() #直接访问包环境内的对象

attach(data) #将data环境加入搜索路径，变量即为对象
detach(data) #将data环境移出搜索路径
with(data, plot(x, y)) #直接访问数据框环境内的变量

ls() #列出`.GlobalEnv`中的对象
ls(3) #列出搜索空间第3位环境中的对象
rm(x) #删除`.GlobalEnv`中的对象x
rm(list = ls()) #删除`.GlobalEnv`中的所有对象
```
