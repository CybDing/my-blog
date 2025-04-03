---
{"dg-publish":true,"permalink":"/math-01-numerical-analysis/01-error-analysis/"}
---


## 误差分析
- 绝对误差 $e = x-\tilde{x}$
- 相对误差 $\delta_{x}= \dfrac{x-\tilde{x}}{x}$
  p.s. 以上都需要知道真值进行分析
### 浮点数系
- 十进制 $0.a_{1}a_{2}a_{3}\cdots a_{n}\times 10^{m}$
- $\beta$进制 $fl(x)=\tilde{x}=\pm (\frac{x_{1}}{\beta^1}+\frac{x_{2}}{\beta^{2}}\cdots +\frac{x_{n}}{\beta^t})\times \beta^{l}$
	- 绝对误差限(舍入误差导致): $\frac{1}{2}\beta^{l-t}$
	- 相对误差限: $\frac{1}{2}\beta^{1-t}$
	- p.s. 有效位数越多，绝对与相对误差相对更小
浮点数系可以使用 $F(\beta, t, L, U)$表示，分别表示进制, 有效位数, 指数位的上界与下界
- $\star$ 浮点数系的范围: $fl_{\min}(x)=\beta^{1-L}\leq|fl(x)|\leq \beta^U\cdot(1-\beta^t)$
  p.s. $fl(x)$中的第一位$x_{1}$不能取$0$, 浮点数系有一般可以表示正负, 浮点数系还需要包含$0$.
- $\star$ 浮点数系的个数: $2(\beta-1)\times \beta^{t-1}\times(U-L+1)+1$
### 条件数
- Def. 对于函数 $f(x)$在 $x$ 处，可以计算对应函数的条件数$Cond(x)$$\frac{|f(x)-f(\tilde{x})|}{|f(x)|}=Cond(x)\times \frac{|x-\tilde{x}|}{|x|}\approx|x \frac{f^{'}(x)}{f(x)}|$
- 我们一般会把条件数大于 $1$ 称为是病态的，而条件数小于$1$可以称误差是可以控制的
### 数值算法 
- 浮点运算(flop): 计算机完成一次浮点乘法(除法)
  p.s. 浮点加法与减法计算时间基本可以忽略
- 矩阵乘法的浮点运算数 $A_{m\times n}*B_{n\times p}$ 需要 $m\times n\times p$次浮点运算(乘法)