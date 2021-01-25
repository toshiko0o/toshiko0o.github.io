---
title: Peskin & Schroeder Book of QFT（持续更新）
date: 2020-10-20 12:20:35
categories: 
- 笔记
tags: 
- QFT
- 物理
- ☆
mathjax: true
---

# Chapter 1 - Invitation

*Pair Production in $e^+e^-$ Annihilation*

# Chapter 2 - The Klein-Gordon Field

## 2.1 The Necessity of the Field Viewpoint

### P.14 Eq1

$\quad U(t)$ when $E = \mathbf{p}^2/2m$ , 
$$
\begin{equation}
\begin{aligned}
U(t) &= \langle \mathbf{x}|e^{-i(\mathbf{p}^2/2m)t}|\mathbf{x}_0\rangle \nonumber \\ 
     &= \int d^3p \langle \mathbf{x}| e^{-i(\mathbf{p}^2/2m)t} |\mathbf{p}\rangle \langle \mathbf{p}| \mathbf{x}_0 \rangle \nonumber \\ 
     &= \int d^3p \ e^{-i(\mathbf{p}^2/2m)t} \langle \mathbf{x}|\mathbf{p}\rangle \langle \mathbf{p}| \mathbf{x}_0\rangle \nonumber \\ 
     &= \int d^3p \ e^{-i(\mathbf{p}^2/2m)t} \biggl(\frac{1}{2\pi}\biggr)^\frac{3}{2} e^{i\mathbf{p}\cdot\mathbf{x}} \biggl(\frac{1}{2\pi}\biggr)^\frac{3}{2} e^{-i\mathbf{p}\cdot\mathbf{x}_0} \nonumber \\ 
     &= \frac{1}{(2\pi)^3} \int d^3p \ e^{-i(\mathbf{p}^2/2m)t} e^{i\mathbf{p}\cdot(\mathbf{x}-\mathbf{x}_0)} \nonumber \\ 
     &= \frac{1}{(2\pi)^3} \int d^3p \ e^{-\frac{it}{2m} [\mathbf{p}-\frac mt(\mathbf{x}-\mathbf{x}_0)]^2} e^{\frac{it}{2m} \cdot \frac{m^2}{t^2} (\mathbf{x}-\mathbf{x}_0)^2} \nonumber \\ 
     &= \frac{1}{(2\pi)^3} \biggl(\frac{2m\pi}{it}\biggr)^\frac{3}{2} e^{im(\mathbf{x}-\mathbf{x}_0)^2/2t}  \nonumber \\ 
     &= \biggl(\frac{m}{2\pi it}\biggr)^\frac{3}{2} e^{im(\mathbf{x}-\mathbf{x}_0)^2/2t} 
\end{aligned}
\end{equation}
$$

The 6th line is the Gaussian Integral. 

### P.14​ Eq2

$\quad U(t)$ when $E = \sqrt{\mathbf{p}^2+m^2}$ , 
$$
\begin{equation}
\begin{aligned}
U(t) &= \mathinner{\langle \mathbf{x}|}e^{-it\sqrt{\mathbf{p}^2+m^2}}\mathinner{|\mathbf{x}_0\rangle} \nonumber \\
     &= \frac{1}{(2\pi)^3} \int d^3p \ e^{-it\sqrt{\mathbf{p}^2+m^2}} e^{i\mathbf{p}\cdot(\mathbf{x}-\mathbf{x}_0)} \nonumber \\ 
     &= \frac{1}{(2\pi)^3} \int p^2\sin\theta dp d\theta d\varphi \ e^{-it\sqrt{p^2+m^2}} e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \nonumber \\ 
     &= \frac{1}{(2\pi)^2} \int_0^\infty p^2 dp \ e^{-it\sqrt{p^2+m^2}} \int_0^\pi d\theta \sin\theta \ e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \nonumber \\
     &= \frac{i}{(2\pi)^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ e^{-it\sqrt{p^2+m^2}} \int_0^\pi d(ip|\mathbf{x}-\mathbf{x}_0|\cos\theta) \ e^{ip|\mathbf{x}-\mathbf{x}_0|\cos\theta} \nonumber \\
     &= \frac{i}{(2\pi)^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ e^{-it\sqrt{p^2+m^2}} (e^{-ip|\mathbf{x}-\mathbf{x}_0|}-e^{ip|\mathbf{x}-\mathbf{x}_0|}) \nonumber \\
     &= \frac{1}{2\pi^2|\mathbf{x}-\mathbf{x}_0|} \int_0^\infty dp \ p\ \sin(p|\mathbf{x}-\mathbf{x}_0|) e^{-it\sqrt{p^2+m^2}} 
\end{aligned}
\end{equation}
$$
From the 2nd line to the 3rd line, we set the direction of $(\mathbf{x}-\mathbf{x}_0)$ to be the direction of z-axis. 

### P.15 Figure 2.1





# Chapter 3 - The Dirac Field