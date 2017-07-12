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

#### Theorem: Sample Variance

Let $\overline X$ be the sample of a random sample of size $n$ from a distribution with mean $\mu$ and variance $\sigma ^2$. Then $Var \overline X = E[(\overline X - \mu)^2] = \frac 1 n \sigma ^2$

Since $\begin{align}Var \overline X = Var (\frac 1 n \sum^n_{k=1}X_k) = \frac 1 {n^2}Var (\sum^n_{k=1}X_k)\end{align}$, then check `ve401_note_4`, we can see a fact that $Var(X+Y) = Var X + Var Y + \text{Cov}(X, Y)$, where $\text{Cov}(X, Y) = E[(X - \mu_X) (Y - \mu_Y)]$, then we get $\begin{align}Var \overline X = \frac 1 {n^2} n Var X = \frac 1 n \sigma ^2\end{align}$

The standard deviation of $\overline X$ is given by $\sqrt{Var \overline X} = \sigma / \sqrt n$ and is called standard error of mean.

