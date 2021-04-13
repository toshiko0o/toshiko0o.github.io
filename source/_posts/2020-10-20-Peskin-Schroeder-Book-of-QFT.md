---
title: Peskin & Schroeder Book of QFT（持续更新）
date: 2020-10-20 12:20:35
categories: 
- 物理笔记
tags: 
- QFT
- 物理
mathjax: true
---

　　这是一篇Peskin book的学习笔记，主要对一些复杂的计算和难以理解的段落（参考前人的笔记）作了注释。由于计算相当困难，并且许多概念及物理图像也需经仔细思考后才能理解，故本篇笔记将以中文呈现。若后有闲暇，将转译为英文。

<!--more-->

# Chapter 1 - Invitation

*Pair Production in $e^+e^-$ Annihilation*

# Chapter 2 - The Klein-Gordon Field

## 2.1 The Necessity of the Field Viewpoint

　　这里提到需要将场量子化的一个原因是：由于爱因斯坦关系$E = mc^2$的存在，任何相对论性过程中都有可能出现正负粒子对，所以用只对单个粒子进行了量子化的理论去解释是不够的。而对于能量较低的情况，我们可以考虑一个存在时间极短的态，此时由于不确定性原理 $\Delta E \cdot \Delta t = \hbar /2$ 的存在，会产生很多“虚粒子”，所以场论（多粒子/可以处理不定数目自由度的理论）是必要的。

　　同时还有一个原因是关于因果性的。下面的计算就是关于传播振幅$U(t)$的计算，他们全都违背了因果性。

### P.14 Eq-1

　　$E = \mathbf{p}^2/2m$时，$U(t)$为：
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

　　$E = \sqrt{\mathbf{p}^2+m^2}$ 时，$U(t)$为：
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





# Chapter 3 - The Dirac Field