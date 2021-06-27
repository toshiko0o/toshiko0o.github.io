---
title: Peskin QFT Note
date: 2021-04-22 18:03:40
categories: 
- 学习笔记
- 物理
tags: 
- QFT
- 物理
mathjax: true
---

　　这是一篇基于 Peskin book 的量子场论学习笔记，主要对一些复杂的计算和难以理解的段落（参考前人的笔记）作了注释，同时根据研究生课程内容对部分较为简略的段落添加了补充说明。由于计算相当困难，并且许多概念及物理图像也需经仔细思考后才能理解，故本篇笔记将以中文呈现。若后有闲暇，将转译为英文。

　　如发现任何错误或遗漏，或希望与我讨论书中的内容，欢迎通过邮件联系。

（如发现有公式显示不全的情况，请尝试反复修改网页缩放。）

<!--more-->

# Chapter 1 - Invitation

*Pair Production in $e^+e^-$ Annihilation*

# Chapter 2 - The Klein-Gordon Field

## 2.1 The Necessity of the Field Viewpoint

　　这里提到需要将场量子化的一个原因是：由于爱因斯坦关系 $E = mc^2$ 的存在，任何相对论性过程中都有可能出现正负粒子对，所以用只对单个粒子进行了量子化的理论去解释是不够的。而对于能量较低的情况，我们可以考虑一个存在时间极短的态，此时由于不确定性原理 $\Delta E \cdot \Delta t = \hbar /2$ 的存在，会产生很多“虚粒子”，所以场论（多粒子理论，可以处理不定数目自由度）是必要的。

　　同时还有一个原因是关于因果性的。下面的计算就是关于传播振幅 $U(t)$ 的计算，结果表明它们违背了因果律。

> 补充 1：关于场的简单理解
>
> 在三维空间中，有 $n$ 个自由度的系统共有 $a=3n$ 个广义坐标，每个广义坐标可以写为 $q_a$。而当我们考虑无限自由度时，$a$ 变为连续参数，$q_a$ 变为函数 $q(a)$，于是我们便得到了“场”。（这只是大概的描述，具体如何从离散变量过渡到场可以参考 *Goldstein* 的第 13 章）
>
> 实际的场是时空坐标 $x^\mu$ 的函数，可以看做某种实体在时空中的**分布**，是一个基础的力学量。

> 补充 2：将要用到的场
>
> - $\phi(x)$：标量场（比如希格斯场）
> - $A_\mu(x)$：矢量场（电磁场）
> - $\psi(x)$：旋量场 

### P.14 - Eq-1

　　$E = \mathbf{p}^2/2m$ 时，$U(t)$ 为：
$$
\begin{equation}
\begin{aligned}
U(t) &= \langle \mathbf{x}|e^{-i(\mathbf{p}^2/2m)t}|\mathbf{x}_0\rangle \\ 
     &= \int d^3p \langle \mathbf{x}| e^{-i(\mathbf{p}^2/2m)t} |\mathbf{p}\rangle \langle \mathbf{p}| \mathbf{x}_0 \rangle \\ 
     &= \int d^3p \ e^{-i(\mathbf{p}^2/2m)t} \langle \mathbf{x}|\mathbf{p}\rangle \langle \mathbf{p}| \mathbf{x}_0\rangle \\ 
     &= \int d^3p \ e^{-i(\mathbf{p}^2/2m)t} \biggl(\frac{1}{2\pi}\biggr)^\frac{3}{2} e^{i\mathbf{p}\cdot\mathbf{x}} \biggl(\frac{1}{2\pi}\biggr)^\frac{3}{2} e^{-i\mathbf{p}\cdot\mathbf{x}_0} \\ 
     &= \frac{1}{(2\pi)^3} \int d^3p \ e^{-i(\mathbf{p}^2/2m)t} e^{i\mathbf{p}\cdot(\mathbf{x}-\mathbf{x}_0)} \\
     &= \biggl(\frac{m}{2\pi it}\biggr)^\frac{3}{2} e^{im(\mathbf{x}-\mathbf{x}_0)^2/2t} . 
\end{aligned}
\end{equation}
$$

　　最后一步直接使用高斯积分公式即可。

　　注：一维高斯积分公式
$$
\begin{equation}
\int_{-\infty}^{\infty}dx\ e^{-cx^2}e^{\pm ibx} = \sqrt{\frac{\pi}{c}}e^{-b^2/4c}. 
\end{equation}
$$

### P.14​ - Eq-2

　　$E = \sqrt{\mathbf{p}^2+m^2}$ 时，$U(t)$ 为：
$$
\begin{equation}
\begin{aligned}
U(t) &= \mathinner{\langle \mathbf{x}|}e^{-it\sqrt{\mathbf{p}^2+m^2}}\mathinner{|\mathbf{x}_0\rangle} \\
     &= \frac{1}{(2\pi)^3} \int d^3p \ e^{-it\sqrt{\mathbf{p}^2+m^2}} e^{i\mathbf{p}\cdot(\mathbf{x}-\mathbf{x}_0)} \\ 
     &= \frac{1}{(2\pi)^3} \int p^2\sin\theta dp d\theta d\varphi \ e^{-it\sqrt{p^2+m^2}} e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \\ 
     &= \frac{1}{(2\pi)^2} \int_0^\infty p^2 dp \ e^{-it\sqrt{p^2+m^2}} \int_0^\pi d\theta \sin\theta \ e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \\
     &= -\frac{i}{(2\pi)^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ e^{-it\sqrt{p^2+m^2}} \int_0^\pi d(ip|\mathbf{x}-\mathbf{x}_0|\cos\theta) \ e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \\
     &= -\frac{i}{(2\pi)^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ e^{-it\sqrt{p^2+m^2}} (e^{-ip|\mathbf{x}-\mathbf{x}_0|}-e^{ip|\mathbf{x}-\mathbf{x}_0|}) \\
     &= \frac{1}{2\pi^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ \sin(p|\mathbf{x}-\mathbf{x}_0|) e^{-it\sqrt{p^2+m^2}}. 
\end{aligned}
\end{equation}
$$
　　在第三行，我们把向量$(\mathbf{x}-\mathbf{x}_0)$的方向设为了 $z$-axis 的正方向。

### P.15 - Figure 2.1

　　两个事件之间的间隔是洛伦兹标量，即
$$
\begin{equation}
(x-x_0)^2 = -s^2,
\end{equation}
$$
因为是类空间隔，所以有个负号。

　　我们把 $x_0$ 作为原点，令 $x'=x-x_0$，空间分量只考虑一维（$x'=(t',x')$），则有
$$
\begin{equation}
x'^2-t'^2=s^2,
\end{equation}
$$
这就是洛伦兹变换下 $x'$ 满足的关系，即为图中所画的双曲线。

## 2.2 Elements of Classical Field Theory

　　注意这里在讨论初末状态时，直接将时空坐标零分量 $x^0$ 取为了定值。实际上在不同的空间点，初末状态的 $x^0$ 可以取不同的值，只需要保证边界是类空超曲面即可。

> 我的理解：只有这样在向空间的无穷远处积分时才能到达时间上的边界。可以画个图感受一下。

### P15 - (2.2) (2.3)

　　这里的
$$
\begin{equation}
\frac{\partial \mathcal{L}}{\partial(\partial_\mu \phi)}\delta(\partial_\mu \phi),
\end{equation}
$$
具体可以写成：
$$
\begin{equation}
\frac{\partial \mathcal{L}}{\partial\dot\phi}\delta  \dot{\phi}+\frac{\partial \mathcal{L}}{\partial(\boldsymbol{\nabla} \phi)}\delta(\boldsymbol{\nabla} \phi),
\end{equation}
$$
　　这里和下面的计算中出现的都不是四矢量的内积，只是各分量偏微分的和的简写（可以全部展开算一遍）。于是最后的 Euler-Lagrange equation 也可以写为
$$
\begin{equation}
\frac{\partial}{\partial t}\biggl(\frac{\partial \mathcal{L}}{\partial\dot\phi}\biggr) + \boldsymbol{\nabla} \biggl(\frac{\partial \mathcal{L}}{\partial(\boldsymbol{\nabla} \phi)}\biggr) - \frac{\partial \mathcal{L}}{\partial \phi} = 0,
\end{equation}
$$
这在利用薛定谔场的 Lagrangian 导出薛定谔方程的时候很有用。

　　而关于这里的边界项 $\partial_\mu \bigl(\frac{\partial \mathcal{L}}{\partial(\partial_\mu \phi)}\delta \phi \bigr)$，注意要分别考虑时间和空间分量（书中也提到了）。

> 补充 ：薛定谔场的 Lagrangian 
> $$
> \mathcal{L}_{Schr\ddot{o}dinger} = i\hbar\psi^\dagger\frac{\partial \psi}{\partial t} - \frac{\hbar^2}{2m}\boldsymbol{\nabla}\psi^\dagger\boldsymbol{\nabla}\psi - V(\mathbf x)\psi^\dagger\psi.
> $$

### P16 - Hamiltonian Field Theorem

　　这里关于哈密顿形式的场论并没有讲完（没有导出运动方程）。导出运动方程要给出场变量和其共轭动量之间的对易/反对易关系，再计算 Heisenberg equation 得到运动方程。

> Heisenberg equation： $i\frac{\partial}{\partial t}\mathcal{O} = [\mathcal{O}, H]$. 

　　Hamiltonian Field Theorem 实际上是和 Lagrangian Field Theorem 不同的路径。而为了保证它能给出正确的运动方程，正则量子化的方法只有两种，也就是上面提到的（等时）对易/反对易关系。

### P17 - Noether's Theorem

　　这里可以参考 Hagen Kleinert 的课程中的[解释](http://users.physik.fu-berlin.de/~kleinert/b6/psfiles/Chapter-7-conslaw.pdf)以及 Weinberg QFT 第一册中的 7.3 一节。

　　Hagen Kleinert 解释了在 (2.11) 中用 Euler-Lagrange 方程的含义：在所有可能的场分布中，我们把处理对象限定于由最小作用量原理决定的那一个，即**真实**的场分布（在经典力学中，即为粒子运动的真实轨道）。

　　我此前的疑惑是：由书中 (2.11) 推导，任意的全局变换（$\alpha$ 为常数）都会导致 Lagrangian 变化一个 4-divergence，这是不是意味着任意的全局变换都是对称变换呢？实际上，这是因为在 (2.11) 中，我们只考虑了**真实**的场分布；而根据 Weinberg 书中的说法，对于**真实**的场分布，确实任意变换都会使 (2.10) 成立。但**对称变换**的含义是该变换使得 (2.10) 对任意场分布都成立，而不仅仅是对**真实**的场分布成立，所以“任意的全局变换都是对称变换”肯定是错误的。

　　所以关于此处所述的 Noether's theorem ，我的理解是这样的：

1. 若某个变换是一个对称变换，则它会使系统的 Lagrangian 变化至多一个 4-divergence，即 (2.10)。需要注意的是，这个变化对于系统中所有可能的场分布都成立，无论是否是满足最小作用量原理的那一个。  

   > 在实际计算时，我们应该首先检查变换是否保证了 (2.10) 成立（书中的前两个例子都是这么做的），并由此得到 $\mathcal{J}^{\mu}$ 的形式。

2. 对于某个具体的变换 (2.9)，我们可以计算得到 (2.11) 式，这代表了变换导致的 Lagrangian 的变化（对一般的场分布）；而接下来，对于真实（满足最小作用量原理）的场来说，考虑其 Lagrangian 的变化需要用 Euler-Lagrange 方程去掉第二项；最后，由于这一项肯定也满足 (2.10)，所以我们令它等于前面的 $\mathcal{J}^{\mu}$，得到守恒流。  

   > 这一步只是为了得到守恒流。

> 补充1: 实际上这里的导数需要替换为李导数
>
> 补充2: 更好的导出守恒流的方式也许是考虑局域变换，详见 Weinberg 书中讲解或 Hagen Kleinert 课件中 8.1.2 一节。

### P18 - (2.13)

$$
\begin{equation}
\begin{aligned}
\frac{dQ}{dt} &= \int \partial_0 j^0 d^3 x \\
&= \int (\partial_\mu j^\mu - \boldsymbol{\nabla}\cdot\mathbf{j}) \ d^3 x \\
& = - \int \boldsymbol{\nabla}\cdot\mathbf{j}\ \ d^3 x \\
&=0.
\end{aligned}
\end{equation}
$$

## 2.3 The Klein-Gordon Field as Harmonic Oscillators
<span id="KG-Field">


### P20 - (2.21) ~ (2.28)

　　这里有一种更好的导出标量场表达式的方法。

　　首先还是将 $\phi(x)$ 表达为
$$
\begin{equation}
\phi(\mathbf{x}, t) = \int \frac{d^3 p}{(2\pi)^3}e^{i\mathbf{p \cdot x}}\phi(\mathbf{p}, t), 
\end{equation}
$$
而其中的 $\phi(\mathbf{p}, t)$ 为（在上式中同时对两端做积分 $\int e^{-i\mathbf{p'\cdot x}} d^3 x$）
$$
\begin{equation}
\phi(\mathbf{p}, t) = \int d^3 x\ e^{-i\mathbf{p \cdot x}}\phi(\mathbf{x}, t), 
\end{equation}
$$
由于 $\phi^\dagger = \phi$ （$\phi$ 为实标量场），
$$
\begin{equation}
\phi^{\dagger}(\mathbf{p}, t) = \int d^3 x\ e^{i\mathbf{p \cdot x}}\phi(\mathbf{x}, t) = -\phi(\mathbf{p}, t). 
\end{equation}
$$
　　接下来考虑运动方程 (2.21)，写出试解：
$$
\begin{equation}
\phi(\mathbf{p}, t) = a_1(\mathbf{p})e^{-i\omega_p t} + a_2(\mathbf{p})e^{i\omega_p t},
\end{equation}
$$
而
$$
\begin{equation}
\phi^{\dagger}(\mathbf{p}, t) = a_1^{\dagger}(\mathbf{p})e^{i\omega_p t} + a_2^{\dagger}(\mathbf{p})e^{-i\omega_p t}.
\end{equation}
$$
　　而 $\phi^{\dagger}(\mathbf{p}, t) = -\phi(\mathbf{p}, t)$ ，则
$$
\begin{equation}
\left\{\begin{array}{c} a_1^{\dagger}(\mathbf{p}) = a_2(\mathbf{-p})\\ a_2^{\dagger}(\mathbf{p}) = a_1(\mathbf{-p})\end{array}\right..
\end{equation}
$$
于是 $\phi(x)$ 可以表示为：
$$
\begin{equation}
\begin{aligned}
\phi(\mathbf{x}, t) &= \int \frac{d^3 p}{(2\pi)^3}e^{i\mathbf{p \cdot x}}\Bigl(a_1(\mathbf{p})e^{-i\omega_p t} + a_2(\mathbf{p})e^{i\omega_p t}\Bigr) \\
&= \int \frac{d^3 p}{(2\pi)^3}\Bigl(a_1(\mathbf{p})e^{-i\omega_p t +i\mathbf{p \cdot x}} + a_1^{\dagger}(-\mathbf{p})e^{i\omega_p t+i\mathbf{p \cdot x}}\Bigr) \\
&= \int \frac{d^3 p}{(2\pi)^3}\Bigl(a_1(\mathbf{p})e^{-i\omega_p t + i\mathbf{p \cdot x}} + a_1^{\dagger}(\mathbf{p})e^{i\omega_p t - i\mathbf{p \cdot x}}\Bigr) \\
&= \int \frac{d^3 p}{(2\pi)^3} \frac{1}{\sqrt{2 \omega_\mathbf{p}}} \Bigl(a(\mathbf{p})e^{-ipx} + a^{\dagger}(\mathbf{p})e^{+ipx}\Bigr).
\end{aligned}
\end{equation}
$$
（这里我们将 $a_1(\mathbf{p})$ 替换为了 $\frac{1}{\sqrt{2\omega_\mathbf{p}}} a(\mathbf{p})$）

　　值得注意的是，书中把 $a(\mathbf{p})$ 写为了 $a_\mathbf{p}$，实际上理解为函数就可以了。熟悉了以后这样写比较方便。

### P21 - (2.26) 下面那一段

　　关于求 $a_\mathbf{p}$ 和 $a^{\dagger}_\mathbf{p}$ 的表达式：将 (2.25) 和 (2.26) 系数凑合适，加减消去其中一个后，再同时对两端做积分 $\int e^{-i\mathbf{p'\cdot x}} d^3 x$ 即可，确实很 easy，Peskin 没有骗你。

### P22 - (2.33)

　　此处计算（以及相关的许多计算）可能要用到如下的关系：
$$
\begin{equation}
\begin{aligned}
\int_{-\infty}^{+\infty}\frac{d^3 p}{(2\pi)^3}f(\mathbf p) &= \int_{+\infty}^{-\infty}\frac{d^3 (-p)}{(2\pi)^3}f(-\mathbf p) \\
&= -\int_{+\infty}^{-\infty}\frac{d^3 p}{(2\pi)^3}f(-\mathbf p) \\
&= \int_{-\infty}^{+\infty}\frac{d^3 p}{(2\pi)^3}f(-\mathbf p).
\end{aligned}
\end{equation}
$$

### P22 - (2.34)

　　建议记这个公式：
$$
\delta(f(x)) = \sum_i \frac{\delta(x-x_i)}{|f'(x_i)|},
$$
其中 $x_i$ 是 $f(x)$ 的根。参考 [$\delta$ 函数的维基百科页面](https://zh.wikipedia.org/wiki/狄拉克δ函数#與函數的復合)。

### P23 - (2.40)

$$
\begin{equation}

\end{equation}
$$



## 2.4 The Klein-Gordon Field in Space-Time

　　我们在[前面](#KG-Field)就已经得到了包含时间的形式。

## Problems

### 2.1



### 2.2



### 2.3

　　略

# Chapter 3 - The Dirac Field

**注意**：本书中的变换都是对场本身进行操作。  
　　　*"active" point of view*

## 3.1 Lorentz Invariance in Wave Equations

### P36 - (3.3)

　　这里只要把 $(\Lambda^{-1}x)$ 看作是 $x$ 的某个函数 $y(x) = \Lambda^{-1}x$，做复合函数的求导即可。等式右端最后那个括号的意思是前面的函数 $\partial_{\nu}\phi$ 在 $\Lambda^{-1}x$ 处取值。

