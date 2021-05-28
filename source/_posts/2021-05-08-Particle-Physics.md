---
title: Particle Physics
date: 2021-05-08 20:56:36
categories: 
- 物理笔记
tags: 
- HEP
- Particle Physics
- 物理
mathjax: true
---

　　课程教材：[Mark Thomson - Modern Particle Physics - Cambridge University Press (2013)](http://libgen.rs/book/index.php?md5=872DC0A962ED5730B605FB1FFA87216E)

　　这本书我也上传到了我的 telegram channel. 

<!--more-->

# 1 - Introduction

*关于基本粒子和相互作用的比较简单和基础的事实。*

## 1.1

　　搞清楚有哪些基本粒子（以及传递相互作用力的粒子），记住他们的一些性质（包括哪些粒子受到哪些力的作用）。具体看看 **Table 1.1**、**Table 1.2** 和 **Table 1.3**。

　　比较重要的是画费曼图。记住 **Fig 1.4** 里的四类顶点。在费曼图中，箭头指向永远是**流进顶点后再流出顶点**，不会出现两个流同时流进（流出）顶点的情况。

　　关于顶点处的耦合系数：$cross\ section\propto |\mathcal{M}|^2$，$\mathcal{M}\propto g^n$，其中 $g$ 是耦合系数，$n$ 是费曼图中相关顶点的个数。但因为我们总是用到 $|\mathcal{M}|^2$，所以定义一个正比于 $g^2$ 的无量纲常数很方便。比如 QED 中的精细结构常数 $\alpha = \frac{e^2}{4\pi\varepsilon_0 \hbar c} \approx \frac{1}{137}$。

　　有多种可能的过程同时发生的时候，强$>$电磁$>$弱。

## 1.2

　　在粒子对撞实验产生的粒子中，稳定的只有电子、质子、光子和很难探测到的中微子。

　　平均寿命在 $\sim 10^{-10}{\rm s}$ 以上的相对论性粒子在衰变前会飞过大概几米的距离，因此也能被探测到。这样的粒子包括：$\mu$ 子（$\mu^{\pm}$）、中子 n（ddu）、带电 $\pi$ 介子（$\pi^{+}({\rm u\bar{d}})$ / $\pi^{-}({\rm d \bar{u}})$）以及带电 K 介子（$\rm K^{+}({\rm u\bar{s}})$ / $\rm K^{-}({\rm s \bar{u}})$）。

- 带电粒子的探测

　　高能带电粒子穿过某种物质时会电离原子中的电子，从而损失能量。这个能量损失（每单位距离）主要和 $\beta \gamma$ 以及物质的密度 $\rho$ 有关。

　　造成 $\mu$ 子的能量损失的主要过程是原子的电离（100 GeV 以下时），所以 $\mu$ 子穿透力极强（能够飞行几米）！因此，加速器产生的 $\mu$ 子常常会穿过整个探测仪器。

- 光子和电子的探测
- 强子的探测

## 1.3



## 1.4

　　**重要！**

　　质心系下的能量（实验中可以用来产生粒子的有效能量）$\sqrt s$ 计算方法：
$$
\begin{equation}
s = \biggl(\sum_{i=1}^{2}E_i\biggr)^2-\biggl(\sum_{i=1}^{2}\mathbf{p}_i\biggr)^2.
\end{equation}
$$

# 2 - Underlying concepts

*介绍自然单位制、复习狭义相对论和非相对论性量子力学。*

## 2.1

　　介绍了自然单位制（多用用就熟悉了）。

　　有趣的事实：$[\hbar,\ c,\ {\rm GeV}]$ 单位制中，

- $\hbar = 1.055 \times 10^{-34}\ {\rm J \cdot s}$ 是**作用量**的最小单位；
- $c = 2.998 \times 10^{-10}\ {\rm m\cdot s^{-1}}$ 为真空中的光速
- $1\ {\rm GeV} = 1.602 \times 10^{-10}\ {\rm J}$ 接近质子的静质量。

　　**Table 2.1**相当有用。

　　速算用转换系数：$\hbar c = 0.197\ {\rm GeV \cdot fm}$ （非常有用！）

　　在 Heaviside-Lorentz 单位制下，精细结构常数为
$$
\begin{equation}
\alpha = \frac{e^2}{4\pi} \approx \frac{1}{137},
\end{equation}
$$
由于它是无量纲常数，由此可以定义自然单位制中的单位电荷 $e = \sqrt{4\pi \alpha} \approx 0.3028$。

## 2.2

### P33 (2.2)

　　关于 $s^2$ 为什么是不变的讨论，可以参考[这篇](https://cds.cern.ch/record/1481640/files/978-3-642-30385-2_BookBackMatter.pdf)和[这篇](https://physics.stackexchange.com/a/478042)。简单的理解是，当我们对这个量做洛伦兹变换的时候，它确实是不变的，所以以它为基础引入闵氏空间的度规是合适的。（个人理解，不一定对）

### P35 (2.9)

　　注意，下标在后的洛伦兹变换（${\Lambda^{\mu}}_{\nu}$）代表正向的洛伦兹变换；而下标在前（${\Lambda_{\mu}}^{\nu}$）的代表洛伦兹变换的逆。

### P37

　　多粒子系统的四动量（给出了**系统的不变质量**）：
$$
\begin{equation}
p^{\mu}p_{\mu} = \biggl(\sum_{i=1}^{n}E_i\biggr)^2-\biggl(\sum_{i=1}^{n}\mathbf{p}_i\biggr)^2.
\end{equation}
$$



# 3 - Decay rates and cross sections

*相对论量子力学中关于截面和衰变率的计算。*

## 3.1

　　

## 3.5

　　

# 4 - The Dirac equation

*狄拉克方程*

## 4.1 

　　简要介绍了 Klein-Gordon方程以及相关的负能量负概率问题，看看就行了。

## 4.2 

　　

