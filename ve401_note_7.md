# Introduction to Statistical Method

## Simultaneous Estimation of the Mean and Variance

### Chi Random Variable

Consider a problem:

-   $z= (z_1, \cdots, z_n) \in \mathbb{R}^n$ randomly chosen.
-   the value $z_k$ is determined by random variable $Z_k$, following a standard normal distribution.
-   think about distribution about $\chi_n := \sqrt {\sum^n_{i=1}Z_i^2}$
-   $\chi_n$ is a chi random variable, follows chi distribution with $n$ degree of freedom.

#### Cumulative Distribution Function

$\begin{align}F_{\chi_n}(y) = P[\chi_n \leq y] = P[\chi_n^2 \leq y^2] = P[\sum^n_{i=1}Z_i^2 \leq y^2] = \int_{\sum^n_{k=1} z_k^2 \leq y^2} f_{Z_1 ...Z_n} (z_1, \cdots, z_n) dz_1 ...dz_n\end{align}$

Since they are $Z_1, ...Z_n$ that $n$ independent standard variables, then we see the joint density:

$\begin{align}f_{Z_1 ...Z_n}(z_1, ...z_n) = \frac 1 {(2\pi)^{n/2}}e^{-\sum^n_{k=1}z_k^2/2}\end{align}$

Thus $\begin{align}F_{\chi_n}(y) = \int_{\sum^n_{k=1}z_k^2 \leq y^2} (2\pi)^{-n/2}e^{-\sum^n_{k=1}z_k^2/2} dz_1 ...dz_n \end{align}$

Apply polar coordinate with $(r, \theta_1, ..., \theta_0)$ with $r > 0$, $0 < \theta_{n-1} < 2\pi$ and $-\pi/2 < \theta_k < \pi/2$ for $k=1,...n-2$:

<img src="./ve401_note_pic/p308.png" alt="Drawing" style="width: 200px;"/>

Then the integral become: <img src="./ve401_note_pic/p309.png" alt="Drawing" style="width: 350px;"/>

Since $D(\theta_1, ...\theta_{n-1})$ is independent of $r$, $\begin{align}C_n = (2\pi)^{-n/2}\int^{2\pi}_0\int^{\pi/2}_{-\pi/2}\cdots \int^{\pi/2}_{-\pi/2}D(\theta_1,...\theta_{n-1})d\theta_1\cdots d\theta_{n-1}\end{align}$

we have $\begin{align}F_{\chi_n}(y) = C_n \int^y_0e^{-r^2/2}r^{n-1}dr\end{align}$.

Obviously, the $\begin{align} 1 = \lim_{y\to \infty} C_n \int _0^\infty e^{-r^2/2}r^{n-1}dr = C_n\Gamma(\frac n 2)2^{n/2-1}\end{align}$

Thus $C_n = (\Gamma(\frac n 2)2^{n/2-1})^{-1}$ and $f_{\chi_n}(y) = \frac 2 {\Gamma(\frac n 2)2^{n/2}} y^{n-1} e^{-y^2/2}$

### Chi-Squared Distribution

we hence derive from the $\begin{align}F_{\chi_n^2} =(\Gamma(\frac n 2)2^{n/2-1})^{-1} \int ^{\sqrt y}_0 e^{-r^2/2} r^{n-1} dr \end{align}$

$\begin{align}f_{\chi_n^2} = F'_{\chi^2_n}(y) = (\Gamma(\frac n 2)2^{n/2-1})^{-1} e^{-y/2} \sqrt y ^{n-1} \cdot \frac d {dy} \sqrt y = \frac 1 {2^{n/2}\Gamma(\frac n 2)}y^{n/2-1}e^{-y/2}\end{align}$

### Sum of Independent Chi-Squared Variables

Given $\begin{align} \chi_m^2 = \sum^m_{i=1}X_i^2 \end{align}$ and $\begin{align} \chi_n^2 = \sum^n_{j=1}Y_j^2 \end{align}$, then $\begin{align} \chi_{m+n}^2 = \chi_m^2 + \chi_n^2 = \sum^m_{i=1}X_i^2 + \sum^n_{j=1}Y_j^2\end{align}$

It follows a chi-squared distribution, but with $m+n$ degree of freedom.

It extends to multi-addition case, trivial.

<div style="page-break-after: always;"></div>

### Joint Sampling of Mean and Variance

In the previous chapter, we were able to analyze the sample mean, and also its distribution, under the assumption of known variance.

If variance $\sigma^2 = E[(X -\mu)^2]$ is unknown, then we must first see $S^2 = \frac 1 {n-1}\sum^n_{k=1}(X_k-\overline X)^2$

So we are using the random sample $X_1, \dots X_n$ to get $\overline X $ and $S^2$ at same time.

So we are getting the joint distribution of $\overline X$ and $S^2$.

#### Theorem

##### Predicate

-   $X_1, \dots X_n$ $n \geq 2$ be a random sample of size $n$.
-   Normal distribution with $\mu$ and variance $\sigma^2$.

##### Content

-   The sample mean $\overline X$ is independent of the sample variance $S^2$.
-   $\overline X$ is normally distributed with mean $\mu$ and $\sigma^2 / n$.
-   $(n-1)S^2/\sigma^2$ is chi-squared distributed with $n-1$ degree of freedom.

### Helmert Transformation

The Helmert transformation is a very special kind of orthogonal transformation from a set of $n \geq 2$ normal random variables $X_1, \dots X_n$ to a new set of random variables $Y_1, \dots Y_n$.

<img src="./ve401_note_pic/p317.png" alt="Drawing" style="width: 250px;"/>

<img src="./ve401_note_pic/p318.png" alt="Drawing" style="width: 300px;"/>

The matrix $A$ is orthonormal since $A^{-1} = A^T$. This implies $|\det A| = 1$.

$\begin{align}\sum^n_{i=1}y_i^2 = \langle y,y \rangle = \langle Ax, Ax\rangle = (Ax)^T(Ax) = x^TA^TAx = \langle A^TAx, x\rangle = \langle x , x\rangle = \sum ^ n _{i=1} x_i^2 \end{align}$

Thus the joint distribution: <img src="./ve401_note_pic/p319.png" alt="Drawing" style="width: 350px;"/>

Apply back into the $y_n$, <img src="./ve401_note_pic/p320.png" alt="Drawing" style="width: 350px;"/>

Then $\begin{align} f_{Y_1}(y_1) = (2\pi)^{-1/2}\sigma^{-1}e^{-\frac 1 {2\sigma^2}(y_1 - \sqrt n \mu)^2} \end{align}$ and $\begin{align} f_{Y_i}(y_i) = (2\pi)^{-1/2}\sigma^{-1}e^{-\frac 1 {2\sigma^2} y_i^2} \end{align}$ for $2 \leq i \leq n$.

$f_{Y_1\dots Y_n}(y_1, \dots y_n) = f_{Y_1}(y_1)\cdot f_{Y_2}(y_2) \dots f_{Y_n}(y_n)$

So $Y_1$ is normally distributed with mean $\sqrt n \mu$ and variance $\sigma^2$, while $Y_2 \dots Y_n$ are having mean 0 and variance $\sigma^2$.

### Proof for Previous Theorem

So $\overline X = n^{-1/2} Y_1$ and $\begin{align}(n-1)S^2 &= \sum^n_{k=1}(X_k - \overline X)^2 = \sum^n_{k=1}X_k^2 - 2\sum^n_{k=1}X_k\overline X + n\overline X^2\\& = \sum^n_{k=1}X_k^2 - n\overline X^2 = \sum^n_{k=1}Y_k^2 - Y_1 ^2= \sum^n_{k=2}Y_k^2\end{align}$

Since $\overline X = n^{-1/2} Y_1$ and $\begin{align} f_{Y_1}(y_1) = (2\pi)^{-1/2}\sigma^{-1}e^{-\frac 1 {2\sigma^2}(y_1 - \sqrt n \mu)^2} \end{align}$, then according to the rule in `ve401 note 3 page 6` that we get $\begin{align}f_{\overline X}(x) = (2\pi)^{-1/2}\sigma^{-1}e^{-\frac 1 {2\sigma^2}(\sqrt n x - \sqrt n \mu)^2}\sqrt n \end{align}$

So the $\overline X$ is normally distributed with mean $\mu$ and variance $\sigma^2 / n$.

$(n-1)S^2 / \sigma^2 = \frac 1 {\sigma^2} \sum^n_{k=2}Y_k^2 = \sum^n_{k=2} (\frac {Y_k} \sigma)^2$ is a chi-squared distribution with $n-1$ freedom.

### Independence of Sample Mean and Sample Variance in more General Form

The converse result for the previous theorem is also true:

$X_1 \dots X_n$, with $n \geq 2$ be independent identical distributed random variables.

If $\overline X$ and $S^2$ are independent, then $X_k$ with $k=1\dots n$ follows normal distribution.

This means that the independence of $\overline X$ and $S^2$ is a characteristic property of the normal distribution. If in a given situation we assume that $\overline X$ and $S^2$ are independently distributed we essentially assuming that the population is normally distributed.

<div style="page-break-after: always;"></div>

### Interval Estimation of Variability

We let $0 < \alpha < 1$ and we define $\chi_{1-\alpha / 2, n}^2 \leq \chi_{\alpha / 2, n}^2 \in \mathbb R$

We use the previous theorem to find a confidential interval for the variance based on sample variance $S^2$.

<img src="./ve401_note_pic/p325.png" alt="Drawing" style="width: 250px;"/>

Thus we get $\begin{align}1-\alpha = P[\chi^2_{1-\alpha/2, n-1} \leq \frac {(n-1)S^2}{\sigma^2} \leq \chi^2_{\alpha/2, n-1}]\end{align}$

Then $\begin{align}1-\alpha = P[\frac {(n-1)S^2}{\chi^2_{\alpha/2, n-1}} \leq \sigma^2 \leq \frac {(n-1)S^2}{\chi^2_{1-\alpha/2, n-1}}] \end{align}$, which is the $100(1-\alpha)\%$ confidence interval for $\sigma^2$.

### Interval Estimation for Mean in Variance Unknown

If we know the variance, then $Z = \frac {\overline X - \mu}{\sigma / \sqrt n}$.

Our main goal is to derive a general formula for a confidence interval on the mean when the value of $\sigma$ is not known and must be estimated.

So we should know the distribution of $\frac {\overline X - \mu}{S / \sqrt n}$.

### T-distribution

-   $Z$ is a standard normal variable.
-   $\chi^2_\gamma$ be an independent chi-squared random variable with $\gamma$ degree of freedom.
-   $T_\gamma = \frac Z {\sqrt{\chi_\gamma^2/\gamma}}$ is a T-distribution with $\gamma$ degree of freedom.

The density for a T distribution with $\gamma$ degrees of freedom is given by:

$\begin{align} f_{T_\gamma}(t) = \frac {\Gamma((\gamma + 1)/ 2)}{\Gamma(\gamma / 2)\sqrt{\pi\gamma}} (1 + \frac {t^2}\gamma)^{-\frac {\gamma + 1}2} \end{align}$ check page 332 to 335

So $X_1 \dots X_n$ be a random sample from a normal distribution with mean $\mu$ and variance $\sigma^2$.

The random variable $T_{n-1} = \frac {\overline X - \mu}{S / \sqrt n}$ follows T distribution with $n-1$ degree of freedom.

(Come from the $(\overline X - \mu) / (\sigma / \sqrt n)$ as standard normal and $(n-1)S^2 / \sigma^2$ as chi-squared with $n-1$ degree of freedom, put them into $T_\gamma$ )

<div style="page-break-after: always;"></div>

### Interval Estimation of Mean with Variance Unknown

We define $t_{\alpha / 2, n} \geq 0$ by $\begin{align}\int^\infty_{t_{\alpha / 2, n}} f_{T_n}(t)dt = \alpha / 2 \end{align}$ <img src="./ve401_note_pic/p337.png" alt="Drawing" style="width: 250px;"/>

#### Theorem

$X_1, \dots X_n$ be a random sample of size $n$ from a normal distribution with mean $\mu$ and variance $\sigma^2$.

The $100(1-\alpha)\%$ confidential interval on $\mu$ is given by $\overline X \pm t_{\alpha / 2, n-1}S / \sqrt n$

### Tolerance Limits

A tolerance interval determined from a sample of size $n$ consists of two numbers $L1, L2$, called tolerance limits.

So it goes like $(1-\alpha) \cdot 100\%$ certainty at least $\delta \cdot 100 \%$ of population lies between $L1, L2$.

Since we know the fact that $95\%$ of the population lies in the interval $\mu \pm 1.96\sigma$.

The $\overline X \pm 1.96 S$ will not always cover $95\%$ of the population since it is a random interval.

#### Theorem: Two-sided Tolerance Limits

$X$ is normally distributed random variable with $\overline X$ and $S^2$ from a sample of size $n$.

$\exists K = K(n,\alpha, \delta)S$ covers at least $\delta \cdot 100\%$ of population with $(1-\alpha)\cdot 100\%$ confidence.

So the $K$ is a two-sided tolerance limit.

