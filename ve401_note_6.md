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