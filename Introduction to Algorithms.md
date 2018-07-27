# **Introduction to Algorithms**

## 数学公式

斯特林近似公式：$n! = \sqrt{2\pi n}(\frac n e)^n(1+\Theta(\frac 1 n))$

对于所有$n\ge 1$ ，$n! = \sqrt{2\pi n}(\frac n e)^ne^{a_n}$

$x-1<\lfloor x\rfloor\leq x\leq\lceil x\rceil\leq x+1$

$e^x = 1+x+\frac{x^2}{2!}+\frac{x^3}{3!}+...=\sum\limits_{i=0}^{\infty}\frac{x^i}{i!}$

当$\left|x\right|<1$时，$\ln(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}-\frac{x^4}{4}+\frac{x^5}{5}-...$

对于$x>-1$，$\frac{x}{1+x}\leq\ln(1+x)\leq x$

对于任意常量$a>0$,$\lg^bn=o(n^a)$

几何级数

## 第四章分治策略

代入法，递归树法， 主方法

Strassen算法

代入法求解递归式分两步：

1. 猜测解的形式
2. 用数学归纳法求出解中的常数，并证明解是正确的。

递归树适合用于生成好的猜测。根节点的代价支配了整棵树的代价。

最长简单路径？

