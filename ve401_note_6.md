# Introduction to Statistical Method

## Estimation

-   An **estimator** for a population parameter $\theta$ is a statistic and donated by $\hat{\theta}$.
-   Any given value of $\hat \theta$ is an **estimate**.

### Desirable Properties of a Point Estimator

-   The expected value of $\hat \theta$ should be $\theta$.
-   $\hat\theta$ should have **small variance** for **large sample size**.

### Bias

-   The difference $\theta - E[\hat \theta]$ is the bias of an estimator $\hat \theta$ for a population parameter $\theta$.
-   $E[\hat\theta] = \theta$ means $\hat \theta$ is unbiased.

### Mean Square Error of Estimator

-   The **mean square error** of $\hat \theta$ is defined as $\text{MSE}(\hat\theta) := E[(\hat \theta - \theta)^2]$.
-   The mean square error measures the **overall quality of an estimator**.

$\begin{align}\text{MSE}(\hat\theta)&= E[(\hat\theta - E[\hat\theta]+E[\hat\theta]-\theta)^2]=E[(\hat\theta - E[\hat\theta])^2 + (E[\hat\theta]-\theta)^2 + 2(\hat\theta - E[\hat\theta])(E[\hat\theta]-\theta)]\\&=Var(\hat\theta) + (bias)^2 + 2E[(\hat\theta - E[\hat\theta])(E[\hat\theta]-\theta)]=Var(\hat\theta) + (bias)^2 + 2E[(\hat\theta - E[\hat\theta])](E[\hat\theta]-\theta)\\&=Var(\hat\theta) + (bias)^2 + 2(E[\hat\theta] - E[\hat\theta])(E[\hat\theta]-\theta)=Var(\hat\theta)+(bias)^2\end{align}$

### Sample Mean Variance and Bias

#### Theorem: Unbiased Sample Mean

Let $X_1, \cdots , X_n$ be a random sample of size $n$ from a distribution with mean $\mu$. Then the sample mean $\overline X$ is an unbiased estimator for $\mu$.

Since $\begin{align}\overline X = \frac 1 n \sum ^n _{k=1}X_k\end{align}$, then we see $\mu - E[\overline X] = \mu - \frac 1 n n \mu  = 0$, thus unbiased.

#### Theorem: Sample Average Variance

Let $\overline X$ be the sample of a random sample of size $n$ from a distribution with mean $\mu$ and variance $\sigma ^2$. Then $Var \overline X = E[(\overline X - \mu)^2] = \frac 1 n \sigma ^2$

Since $\begin{align}Var \overline X = Var (\frac 1 n \sum^n_{k=1}X_k) = \frac 1 {n^2}Var (\sum^n_{k=1}X_k)\end{align}$, then check `ve401_note_4`, we can see a fact that $Var(X+Y) = Var X + Var Y + \text{Cov}(X, Y)$, where $\text{Cov}(X, Y) = E[(X - \mu_X) (Y - \mu_Y)]$, then we get $\begin{align}Var \overline X = \frac 1 {n^2} n Var X = \frac 1 n \sigma ^2\end{align}$

The standard deviation of $\overline X$ is given by $\sqrt{Var \overline X} = \sigma / \sqrt n$ and is called standard error of mean.

### Theorem: Sample Variance

Sample variance $\begin{align} S^2 = \frac 1 {n-1} \sum^n_{k=1} (X_k - \overline X)^2 \end{align}$ is an unbiased estimator for $\sigma^2$.

$\begin{align} E[\frac 1 {n-1} \sum^n_{k=1} (X_K-\overline X)^2] &= \frac 1 {n-1}E[\sum^n_{k=1} (X_K-\mu + \mu -\overline X)^2] \\&= \frac 1 {n-1} E[\sum^n_{k=1} (X_k - \mu)^2 - 2(\overline X - \mu) (\sum^n_{k=1} X_k - n\mu) + n(\mu-\overline X)^2]\\&=\frac {1}{n-1}E[\sum^n_{k=1} (X_k - \mu)^2 - n(\mu-\overline X)^2 ] \\&=\frac 1 {n-1} (\sum^n_{k=1}E[(X_k-\mu)^2]- nE[(\mu-\overline X)^2]) = \frac 1{n-1} (\sum^n_{k=1} \sigma^2 - n\frac {\sigma^2}{n}) = \sigma^2 \end{align}$

### Finding Estimator: Method of Moments

-   We have an unbiased estimator $\begin{align} M_k = \frac 1 n \sum^n_{i=1}X_i^k \end{align}$ for the $k^{th}$ moments $E[X^k]$ given random samples $X_1, \cdots, X_n$.
-   The idea is then that population parameters $\theta_j$ can often be expressed in terms of moments of distribution. Replacing the moments in these expressions by their estimators for parameter $\theta_j$.
-   Estimators obtained in this way are not necessarily unbiased.

### Finding Estimator: Method of Maximum Likelihood

-   Assume we have a random sample $x_1, \cdots ,x_n$ from the distribution of a random variable $X$ with density $f$ and parameter $\theta$.
-   Define likelihood function by $\begin{align} L(\theta) = \prod^n_{i=1}f(x_i) \end{align}$.
-   Find the $\theta$ by maximizing the $L(\theta)$.
-   Replace $\theta$ with $\hat \theta$.

### Distribution of Sample Mean

#### Theorem: MGF to distribution function

-   $X, Y$ are two random variables with moments generating functions $m_X, m_Y$.
-   If $m_X(t) = m_Y(t)$ for all $t$ in a neighborhood of zero, then $f_X(t) = f_Y(t)$ for all $x$.

#### Theorem: MGF of Random Variables' Sum

-   $X_1, X_2$ are two random variables with moments generating functions $m_{X_1}, m_{X_2}$.
-   Then if $Y  = X_1 + X_2$, $m_Y = m_{X_1} + m_{x_2}$.

#### Theorem: MGF of Numerical Multiplied Random Variable

-   $X$ be a random variable with MGF $m_X = E[e^{Xt}]$.
-   $Y = \alpha + \beta X$, then $m_Y(t) = E[e^{(\alpha + \beta X)t}] = e^{\alpha t}m_X(\beta t)$.

<div style="page-break-after: always;"></div>

### Two-Sided Confidence Intervals

#### Definition

$0 \leq \alpha \le 1$, a $100(1-\alpha)\%$ (two sided) confidence interval for a parameter $\theta$ is an interval $[L_1, L_2]$ such that $P[L_1 \leq \theta \leq L_2] = 1 - \alpha$.

##### Remark 1

The definition doesn't determine $L_1, L_2$ uniquely.

##### Remark 2

The population parameter $\theta$ is not random, but $L_1, L_2$ are random. Hence $[L_1, L_2]$ is random interval.

### Interval Estimation for Mean

-   random sample of size $n$ from a normal population
-   unknown mean $\mu$ and known variance $\sigma^2$
-   Sample yields point estimate $\overline X$ for $\mu$.
-   We are interested in finding $L = L(\alpha)$ that we can state with $100(1-\alpha)\%$ confidence that $\mu = \overline X \pm L$.

$z_{\alpha / 2}$ defined for $\alpha \in [0, 1]$ with $\begin{align}\alpha / 2 = P[Z \geq z_{\alpha / 2}] = \frac 1 {\sqrt{2\pi}} \int ^\infty_{z_{\alpha/2}} e^{-x^2 / 2}dx =\frac 1 {\sqrt{2\pi}} \int _{-\infty}^{-z_{\alpha/2}} e^{-x^2 / 2}dx \end{align}$

Thus $\begin{align}1-\alpha = P[\overline X - L \leq \mu \leq \overline X + L] = P[\frac {\overline X - \mu - L}{\sigma / \sqrt n} \leq 0 \leq \frac {\overline X - \mu + L}{\sigma / \sqrt n}]\end{align}$ (the later P is standard normal distribution)

Then we let $\begin{align}Z = \frac {\overline X - \mu}{\sigma / \sqrt n}\end{align}$

$\begin{align} 1-\alpha &= P[Z - \frac L {\sigma/\sqrt n} \leq 0 \leq Z + \frac L {\sigma / \sqrt n} ] = P[- \frac L {\sigma/\sqrt n} \leq Z \leq \frac L {\sigma/\sqrt n} ]\\&=2P[0\leq Z \leq \frac L {\sigma/\sqrt n} ] = 1-2P[\frac L {\sigma/\sqrt n} \leq Z \leq \infty] \end{align}$

This means $\begin{align}\frac L {\sigma / \sqrt n} = z_{\alpha / 2} \Leftrightarrow L = \frac {\sigma \cdot z_{\alpha / 2}}{\sqrt n} \end{align}$

#### Theorem

Let $X_1, \cdots, X_n$ be a random sample of size $n$ from a normal distribution with mean $\mu$ and variance $\sigma^2$.

A $100(1-\alpha)\%$ confidence interval on $\mu$ is given by $\overline X \pm \frac {\sigma \cdot z_{\alpha / 2}}{\sqrt n}$

<div style="page-break-after: always;"></div>

### Central Limit Theorem

#### Theorem: General Version

-   Let $X_1, \cdots, X_n$ be independent random variables with arbitrary distributions.

-   $E[X_j] = \mu_j$ and variance $Var X_j = \sigma _j^2$.

-   Under some general conditions:

    $\begin{align} Z_n = \frac {Y - \sum\mu_j}{\sqrt{\sum\sigma_j^2}} \end{align}$ is approximately standard-normally distributed as $n$ gets large.

#### Theorem: Specified Version

-   $E[X] = \mu$ and variance $\sigma^2$.
-   Under some general conditions: $\begin{align} Z_n = \frac {\overline X - \mu}{\sigma / \sqrt n} \end{align}$ is approximately standard normal.

#### Well-behave Judgement

-   Well-behave: nearly symmetric densities that look close to that of a normal distribution

    $n \geq 4$

-   Reasonably behaved: no prominent mode, densities look like uniform densities

    $n \geq 12$

-   Ill behaved: much of the weight of the densities is in the tails, irregular appearance

    $n \geq 100$

