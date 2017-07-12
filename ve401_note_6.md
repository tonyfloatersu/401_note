# Introduction to Statistical Method

## Estimation

An **estimator** for a population parameter $\theta$ is a statistic and donated by $\hat{\theta}$.

Any given value of $\hat \theta$ is an **estimate**.

### Desirable Properties of a Point Estimator

-   The expected value of $\hat \theta$ should be $\theta$.
-   $\hat\theta$ should have **small variance** for **large sample size**.

### Bias

-   The difference $\theta - E[\hat \theta]$ is the bias of an estimator $\hat \theta$ for a population parameter $\theta$.
-   $E[\hat\theta] = \theta$ means $\hat \theta$ is unbiased.

### Mean Square Error of Estimator

-   The **mean square error** of $\hat \theta$ is defined as $\text{MSE}(\hat\theta) := E[(\hat \theta - \theta)^2]$.

-   The mean square error measures the **overall quality of an estimator**.

-   we can derive MSE in another form:

    $\begin{align}\text{MSE}(\hat\theta)&= E[(\hat\theta - E[\hat\theta]+E[\hat\theta]-\theta)^2]\\&=E[(\hat\theta - E[\hat\theta])^2 + (E[\hat\theta]-\theta)^2 + 2(\hat\theta - E[\hat\theta])(E[\hat\theta]-\theta)]\\&=Var(\hat\theta) + (bias)^2 + 2E[(\hat\theta - E[\hat\theta])(E[\hat\theta]-\theta)]\\&=Var(\hat\theta) + (bias)^2 + 2E[(\hat\theta - E[\hat\theta])](E[\hat\theta]-\theta)\\&=Var(\hat\theta) + (bias)^2 + 2(E[\hat\theta] - E[\hat\theta])(E[\hat\theta]-\theta)\\&=Var(\hat\theta)+(bias)^2\end{align}$

### Sample Mean and Bias

#### Theorem: Unbiased Sample Mean

Let $X_1, \cdots , X_n$ be a random sample of size $n$ from a distribution with mean $\mu$. Then the sample mean $\overline X$ is an unbiased estimator for $\mu$.

Since $E[X]$