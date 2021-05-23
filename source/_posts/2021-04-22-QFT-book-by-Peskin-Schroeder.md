---
title: QFT book by Peskin & Schroeder
date: 2021-04-22 18:03:40
categories: 
- 物理笔记
tags: 
- QFT
- 物理
mathjax: true
---

　　这是一篇基于 Peskin book 的量子场论学习笔记，主要对一些复杂的计算和难以理解的段落（参考前人的笔记）作了注释，同时根据研究生课程内容对部分较为简略的段落添加了补充说明。由于计算相当困难，并且许多概念及物理图像也需经仔细思考后才能理解，故本篇笔记将以中文呈现。若后有闲暇，将转译为英文。

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

### P.14 Eq-1

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

　　最后一步直接使用高斯积分公式即可.

　　注：一维高斯积分公式
$$
\begin{equation}
\int_{-\infty}^{\infty}dx\ e^{-cx^2}e^{\pm ibx} = \sqrt{\frac{\pi}{c}}e^{-b^2/4c}. 
\end{equation}
$$

### P.14​ Eq-2

　　$E = \sqrt{\mathbf{p}^2+m^2}$ 时，$U(t)$ 为：
$$
\begin{equation}
\begin{aligned}
U(t) &= \mathinner{\langle \mathbf{x}|}e^{-it\sqrt{\mathbf{p}^2+m^2}}\mathinner{|\mathbf{x}_0\rangle} \\
     &= \frac{1}{(2\pi)^3} \int d^3p \ e^{-it\sqrt{\mathbf{p}^2+m^2}} e^{i\mathbf{p}\cdot(\mathbf{x}-\mathbf{x}_0)} \\ 
     &= \frac{1}{(2\pi)^3} \int p^2\sin\theta dp d\theta d\varphi \ e^{-it\sqrt{p^2+m^2}} e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \\ 
     &= \frac{1}{(2\pi)^2} \int_0^\infty p^2 dp \ e^{-it\sqrt{p^2+m^2}} \int_0^\pi d\theta \sin\theta \ e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \\
     &= \frac{i}{(2\pi)^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ e^{-it\sqrt{p^2+m^2}} \int_0^\pi d(ip|\mathbf{x}-\mathbf{x}_0|\cos\theta) \ e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \\
     &= \frac{i}{(2\pi)^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ e^{-it\sqrt{p^2+m^2}} (e^{-ip|\mathbf{x}-\mathbf{x}_0|}-e^{ip|\mathbf{x}-\mathbf{x}_0|}) \\
     &= \frac{1}{2\pi^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ \sin(p|\mathbf{x}-\mathbf{x}_0|) e^{-it\sqrt{p^2+m^2}}. 
\end{aligned}
\end{equation}
$$
　　在第三行，我们把向量$(\mathbf{x}-\mathbf{x}_0)$的方向设为了 $z$-axis 的正方向. 

### P.15 Figure 2.1

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

### P15 (2.2) (2.3)

　　这里的
$$
\begin{equation}
\frac{\partial \mathcal{L}}{\partial(\partial_\mu \phi)}\delta(\partial_\mu \phi),
\end{equation}
$$
具体可以写成：
$$
\begin{equation}
\frac{\partial \mathcal{L}}{\partial\dot\phi}\delta  \dot{\phi}+\frac{\partial \mathcal{L}}{\partial(\mathbf{\nabla} \phi)}\delta(\mathbf{\nabla} \phi),
\end{equation}
$$
　　所以这里和下面的计算中出现的都不是四矢量的内积，只是各分量偏微分的和的简写（可以全部展开算一遍）。于是最后的 Euler-Lagrange equation 也可以写为
$$
\begin{equation}
\frac{\partial}{\partial t}\biggl(\frac{\partial \mathcal{L}}{\partial\dot\phi}\biggr) + \mathbf{\nabla} \biggl(\frac{\partial \mathcal{L}}{\partial(\mathbf{\nabla} \phi)}\biggr) - \frac{\partial \mathcal{L}}{\partial \phi} = 0,
\end{equation}
$$
这在利用薛定谔场的拉氏量导出薛定谔方程的时候很有用。

　　而关于这里的边界项 $\partial_\mu \bigl(\frac{\partial \mathcal{L}}{\partial(\partial_\mu \phi)}\delta \phi \bigr)$，注意要分别考虑时间和空间分量（书中也提到了）。

> 补充 ：薛定谔场的拉氏量
> $$
> \mathcal{L}_{Schr\ddot{o}dinger} = i\hbar\psi^\dagger\frac{\partial \psi}{\partial t} - \frac{\hbar^2}{2m}\mathbf{\nabla}\psi^\dagger\mathbf{\nabla}\psi - V(\mathbf x)\psi^\dagger\psi.
> $$



# Chapter 3 - The Dirac Field