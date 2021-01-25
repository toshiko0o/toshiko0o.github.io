---
title: Simon Book of Solid State Physics（持续更新）
date: 2020-11-08 17:49:40
categories: 
- 笔记
tags: 
- Solid State Physics
- 物理
- ☆
mathjax: true


---



# Chapter 2 - Specific Heat of Solids

*Boltzmann, Einstein, and Debye*

☆ **Comments on Heat Capacity**

- Heat Capacity: $C_V = \Bigl(\frac{\partial Q}{\partial T}\Bigr)_V = \Bigl(\frac{\partial E}{\partial T}\Bigr)_V$ (For constant volume, $W = 0$). 
- Specific heat: heat capacity *per unit mass* (molar heat capacity sometimes). 
- In this book, almost always concerned with the *heat capacity per atom.*  
  e.g. $C_V$ per atom

## 2.0 Boltzmann's Model

Each atom in the solid is bound to neighboring atoms. For a single particular atom, we imagine it as being in a harmonic well. 

In one dimension,  the energy of one oscillator is 
$$
\begin{equation}
H = \frac{p^2}{2m} + \frac 1 2 kx^2,
\end{equation}
$$
then the partition function is ($\beta = \frac{1}{k_0T}$)
$$
\begin{equation}
\begin{aligned}
Z_{cl} &= \frac{1}{\sqrt{2\pi \hbar ^3}}\int dp \int dx \ \exp{(-\beta H}) \\ 
&= \frac{1}{\sqrt{2\pi \hbar ^3}}\int dp \int dx \ \exp{(-\frac{\beta p^2}{2m}}) \exp{(-\frac{\beta k x^2}{2}}) \\
&= \frac{1}{\sqrt{2\pi \hbar ^3}} \sqrt{\frac{2m\pi}{\beta}}\sqrt{\frac{2\pi}{\beta k}} \\
&= \frac 1 \beta \sqrt{\frac{2\pi m}{\hbar ^3 k}}, 
\end{aligned}
\end{equation}
$$
so the energy of the system will be 

$$
\begin{equation}
E = -\frac{\partial \ln Z_{cl}}{\partial \beta} = \frac 1 \beta = k_0T
\end{equation}
$$


Heat capacity: ($3N$ for $3$ dimensions and $N$ particles)
$$
\begin{equation}
C = \frac{dE}{dT} = 3Nk_0.
\end{equation}
$$

## 2.1 Einstein's Calculation

Eigenstates of a single harmonic oscillator (1-D) are
$$
\begin{equation}
E_n = \hbar \omega (n + 1/2). 
\end{equation}
$$
Here, $\omega$ is called "Einstein frequency", and for "Einstein temperature" $T_\text{Einstein}$, we have
$$
\begin{equation}
\hbar\omega = k_0T_\text{Einstein}.
\end{equation}
$$
So the partition function (1-D) is
$$
\begin{equation}
Z_\text{1-D} = \sum_{n \geqslant 0} e^{\beta \hbar \omega(n + 1/2)} = \frac{e^{-\beta \hbar \omega/2}}{1-e^{-\beta \hbar \omega}} = \frac{1}{2\sinh(\beta \hbar \omega/2)}.
\end{equation}
$$
The expectation of energy is
$$
\begin{equation}
\langle E \rangle = -\frac{1}{Z_\text{1-D}} \frac{\partial Z_\text{1-D}}{\partial \beta} = \frac{\hbar \omega}{2} \coth \biggl(\frac{\beta \hbar \omega}{2} \biggr) = \hbar\omega \biggl(n_\text{B}(\beta \hbar \omega) + \frac 1 2 \biggr) ,
\end{equation}
$$
where the $n_\text{B}$ is the Bose occupation factor
$$
\begin{equation}
n_{\text B}(x) = \frac{1}{e^x - 1}.
\end{equation}
$$

Therefore, $C$ for a single oscillator is
$$
\begin{equation}
C = \frac{\partial \langle E \rangle}{\partial T} = k_0(\beta \hbar \omega)^2\frac{e^{\beta \hbar \omega}}{(e^{\beta \hbar \omega}-1)^2} .
\end{equation}
$$
Because $Z_\text{3-D} = [Z_\text{1-D}]^3$, the $C$ under the three-dimensional case should multiply by 3, 
$$
\begin{equation}
C = 3k_0(\beta \hbar \omega)^2\frac{e^{\beta \hbar \omega}}{(e^{\beta \hbar \omega}-1)^2} .
\end{equation}
$$

## 2.2 Debye's Calculation

### 2.2.1 Periodic Boundary Condition

Possible values of $k$: 
$$
\begin{equation}
k = \frac{2\pi n}{L},
\end{equation}
$$
for large enough $L$:
$$
\begin{equation}
\sum_k \rightarrow \frac L {2\pi} \int^{+\infty}_{-\infty}dk,
\end{equation}
$$
for 3 dimensions, 
$$
\begin{equation}
\sum_\mathbf{k} \rightarrow \frac {L^3} {(2\pi)^3} \int d\mathbf{k}.
\end{equation}
$$

### 2.2.2 Debye's Calculation Following Planck

**Dispersion relation**
$$
\begin{equation}
\omega (\mathbf k) = v|\mathbf k|.
\end{equation}
$$
The expectation of energy (sum over **k** in addition to Einstein's calculation): 
$$
\begin{equation}
\begin{aligned}
\langle E \rangle &= 3 \sum_{\mathbf k}\hbar\omega(\mathbf k)\biggr(n_{\text B}(\beta \hbar\omega(\mathbf k))+\frac 1 2\biggr) \\
&= 3\frac{L^3}{(2\pi)^3}\int d\mathbf {k}\ \hbar\omega(\mathbf k) \biggr(n_{\text B}(\beta \hbar\omega(\mathbf k))+\frac 1 2\biggr) \\
&= \frac{3L^3}{(2\pi)^3}4\pi\int_0^\infty \omega^2 d\omega(1/v^3)(\hbar\omega)\biggr(n_{\text B}(\beta \hbar\omega)+\frac 1 2\biggr) \\
&= \int_0^\infty d\omega \ g(\omega)(\hbar\omega)\biggr(n_{\text B}(\beta \hbar\omega)+\frac 1 2\biggr),
\end{aligned}
\end{equation}
$$

the 3rd line used $k = \omega/v$, and the density of states, $g(\omega)$, is given by
$$
\begin{equation}
g(\omega) = N\frac{9\omega^3}{\omega_{\text d}^3}. 
\end{equation}
$$


Finally, $\langle E\rangle$ is
$$
\begin{equation}
\langle E\rangle = 9N \frac{(k_0 T)^4\pi^4}{(\hbar\omega_{\text d})^3 15}\quad\ +\quad\ T\ \ \text{independent constant.}
\end{equation}
$$
So, $C$ will be
$$
\begin{equation}
C = Nk_0\frac{12\pi^4}{5}\frac{T^3}{\ \ T_{\text{Debye}}^3},
\end{equation}
$$

In equations above, $\omega_d$ and $T_{Debye}$ are defined as
$$
\begin{gather}
\omega_{\text d}  = (6\pi^2n)^{1/3}\ v \\
k_0T_{\text{Debye}} = \hbar\omega_{\text d}
\end{gather}
$$

Here $n$ is the number density. 

### 2.2.3 Debye's "Interpolation"

**There should be only as many modes as there are degrees of freedom in the system.** 

Do not consider sound waves above some maximum frequency $\omega_{\text{cutoff}}$, so define this frequency as
$$
\begin{equation}
3N = \int_{0}^{\omega_{\text{cutoff}}}d\omega\ g(\omega).
\end{equation}
$$
Then we can rewrite $(8)$ as
$$
\begin{equation}
\langle E\rangle = \int_{0}^{\omega_{\text{cutoff}}}d\omega\ g(\omega)(\hbar\omega)\biggr(n_{\text B}( \beta \hbar\omega)+\frac 1 2\biggr).
\end{equation}
$$
For high temperature, 
$$
\begin{equation}
n_{\text B}(\beta\hbar\omega)=\frac{1}{e^{\beta\hbar\omega}-1} \rightarrow \frac{k_0T}{\hbar\omega}.
\end{equation}
$$
Then we will have $\langle E\rangle = 3k_0 TN$ (dropping the term $\frac 1 2$ because it does nothing with $\beta$). 

And if we do the integral of $(15)$ explicitly, we will find $\omega_{\text{cutoff}} = \omega_{\text{d}}$. 

## 2.3 Appendix to this Chapter: $\zeta(4)$ 

Riemann zeta function: 
$$
\begin{equation}
\zeta(p) = \sum_{n=1}^{\infty}n^{-p}.
\end{equation}
$$

The book uses some smart way to get that $\zeta(4) = \pi^4/90$. 

# Chapter 3 - Electrons in Metals

*Drude Theory*

## 3.0 Three Assumptions

1. Electrons have a scattering time $\tau$. The probability of scattering within a time interval $dt$ is $dt/\tau$. 

2. Once a scattering event occurs, we assume the electron returns to momentum $\mathbf p = 0$. 

3. In between scattering events, the electrons, which are charge $−e$ particles, respond to the externally applied electric field $\mathbf E$ and magnetic field $\mathbf B$.

Then the  EoM for electrons is:
$$
\begin{equation}
\frac{d\mathbf p}{dt} = \mathbf F - \frac{\mathbf p}{\tau},
\end{equation}
$$
with $\mathbf F$ to be the Lorentz force: 
$$
\begin{equation}
\mathbf F = -e(\mathbf E + \mathbf v \times \mathbf B).
\end{equation}
$$

## 3.1 Electron in Fields

### 3.1.1 Electron in an Electric Field

$$
\begin{equation}
\frac{d\mathbf p}{dt} = -e\mathbf E - \frac{\mathbf p}{\tau}.
\end{equation}
$$

Consider the steady state, $\frac{d\mathbf p}{dt} = 0$, 

Conductivity:
$$
\begin{equation}
\sigma = \frac{e^2\tau n}{m}.
\end{equation}
$$

### 3.1.2 Electron in Electric and Magnetic Fields

$$
\begin{equation}
\frac{d\mathbf p}{dt} = -e(\mathbf E + \mathbf v \times \mathbf B) - \frac{\mathbf p}{\tau},
\end{equation}
$$

As before, consider the steady state, 
$$
\begin{equation}
\mathbf E = \biggl(\frac{1}{ne}\mathbf j \times \mathbf B + \frac{m}{ne^2\tau} \mathbf j\biggr),
\end{equation}
$$
which we can write as: 
$$
\begin{equation}
\mathbf E = \rho\  \mathbf j. 
\end{equation}
$$
Imagine $\mathbf B$ oriented in the $\hat{z}$ direction, then $\rho$ is given as: 
$$
\begin{gathered}
\rho_{11} = \rho_{22} = \rho_{33} = \frac{m}{ne^2\tau}, \\
\rho_{12} = -\rho_{21} = \frac{|\mathbf B|}{ne}.
\end{gathered}
$$
*Hall resistivity*: Off-diagonal terms of $\rho$.  

*Hall coefficient*: (detailed on [Wikipedia - Hall effect](https://en.wikipedia.org/wiki/Hall_effect)) ($t$ for thickness, and $w$ for width)
$$
\begin{equation}
R_H = \frac{V_H t}{I|\mathbf B|} = \frac{E_2 wt}{j_1 wt|\mathbf B|} = \frac{\rho_{21}j_1}{j_1|\mathbf B|} = \frac{\rho_{21}}{|\mathbf B|} = -\frac{1}{ne}.
\end{equation}
$$

## 3.2 Thermal Transport

**Conductivity $\kappa$:** 
$$
\begin{equation}
\kappa = \frac 1 3 nc_v \langle v \rangle \lambda, 
\end{equation}
$$

where $c_v$ is the heat capacity per particle, which is (for a conventional monatomic gas): 
$$
\begin{equation}
c_v = \frac 3 2 k_0, 
\end{equation}
$$
and 
$$
\begin{gather}
\lambda = \langle v \rangle\tau, \\
\langle v \rangle = \sqrt{\frac{8k_0T}{\pi m}}, \\
\langle v^2 \rangle = \frac{3k_0T}{m}.
\end{gather}
$$
$\kappa$ can be written as: 
$$
\begin{equation}
\kappa = \frac 1 3 n \cdot \frac 3 2 k_0\langle v \rangle^2 \tau = \frac 1 2 n k_0\langle v \rangle^2 \tau, 
\end{equation}
$$
or we can use $\langle v^2 \rangle$ instead: 
$$
\begin{equation}
\kappa = \frac 1 2 n k_0\langle v^2  \rangle \tau, 
\end{equation}
$$
*Lorenz number*: the ratio of thermal conductivity to electrical conductivity, 
$$
\begin{equation}
L = \frac{\kappa}{T\sigma} = \frac 4 \pi \biggl(\frac {k_0} e \biggr)^2 or\ \frac 3 2 \biggl(\frac {k_0} e \biggr)^2, 
\end{equation}
$$
*This calculation is completely incorrect, but two mistakes come together making the result successful.*

**Peltier Effect:** running electrical current through a material also transports heat. 

Peltier coefficient $\Pi$: 
$$
\begin{equation}
\mathbf j ^q = \Pi \mathbf j
\end{equation}
$$
where $\mathbf j^q$ is the heat current density, and $\mathbf j$ is the electrical current density. 

# Chapter 4 - More Electrons in Metals

*Sommerfeld (Free Electron) Theory*

## 4.1 Basic Fermi-Dirac Statistics

Fermi occupation factor $n_\text{F}$: 

$$
\begin{equation}
n_{\text F}(x) = \frac{1}{e^x + 1},
\end{equation}
$$
the probability of an eigenstate of energy $E$ being occupied is then: ($\mu$ is the chemical potential)
$$
\begin{equation}
n_{\text F}(\beta(E-\mu)) = \frac{1}{e^{\beta(E-\mu)} + 1},
\end{equation}
$$


# Chapter 5 - The Periodic Table

## 5.1 Chemistry, Atoms, and the Schrödinger Equation

Nothing to note. 

## 5.2 Structure of the Periodic Table

$|n, l, l_z, \sigma_z \rangle$: denotation of the state of an electron in an atomic orbit. 

$$
\begin{align*}
n &= 1, 2, \ldots \\
l &= 0, 1, \ldots, n-1 \\
l_z &= -l, \ldots, l \\
\sigma_z &= \pm 1/2.
\end{align*}
$$

- **Aufbau Principle**: Shells should be filled starting with the lowest available energy state. An entire shell is filled before another shell is started.
- **Madelung's Rule**: The energy ordering is from lowest value of $(n + l)$ to the largest; and when two shells have the same value of $(n + l)$, fill the one with the smaller n first. 

## 5.3 Periodic Trends

{% asset_image 001.png "Periodic Table"%}

### 5.3.1 Effective Nuclear Charge

# Chapter 6 - Chemical Bonding

## 6.1 Ionic Bonds



## 6.2 Covalent Bond



# Chapter 9 - Vibrations of a 1-D Monatomic Chain

For monatomic chain, compressibility and sound velocity will be: 

**Compressibility**: $$\beta = \frac{1}{\kappa a}$$, 

**Sound velocity**: $$v = \sqrt{\frac{\kappa a^2}{m}}$$. 

Where $$\kappa$$ is the 

