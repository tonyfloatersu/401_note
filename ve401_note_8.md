# Introduction to Statistical Method

## Hypothesis Testing

A second major statistical method for gaining information on a probability.

The goal is to reject or fail to reject statements (hypotheses) based on statistical data.

### Hypothesis Definition

A statement about a population parameter $\theta$. The hypothesis will compare $\theta$ to a null value donated $\theta_0$.

### Fisher's Null Hypothesis Test

This hypothesis will be donated by $H_0$ and is null hypothesis.

Three forms: $H_0: \theta = \theta_0$ or $H_0: \theta\leq \theta_0$ or $H_0: \theta \geq \theta_0$.

A hypothesis test is based on rejecting a hypothesis.

### One-Tailed Test

The test of a hypothesis of the form $H_0:\theta \leq \theta_0$ or $H_0: \theta \geq \theta_0$ is said to be one-tailed tests.

### P-Value for a One-Tailed Test

-   Apply an example first

    We want to find evidence that a new car design has a mean mileage greater than 26 mpg. Therefore, we set up the null hypothesis: $H_0: \mu \leq 26$.

    The goal is to reject the null hypothesis.

-   Example explanation

    We take a random sample and calculate $\overline X$, if it is much greater than 26, then there is reason to believe that $H_0$ is false.

    Take a random sample of size $n$ and find the value $\overline x$ for the sample mean.

    The probability of obtaining the measured value of $\overline x$ or a larger result if $H_0$ is true is the **significance** or **P-Value** of the test.

    (TM还是说中文吧：就是说，猜测$\mu \leq 26$，然后我们得到了样本的平均的观测值$\overline x$，根据样本个数和标准差，我们可以对样本的平均值$\overline X$得到基于$\mu \leq 26$的test，然后可以放宽到$\mu =26$，然后可以用$Z = \frac {\overline X - \mu_0}{\sigma / \sqrt n}$算出$P$的值来判断这个样本是否符合这个假设)

    $P[\overline X \geq \overline x | \mu \leq 26] \leq P[\overline X \geq \overline x | \mu = 26]$

    <img src="./ve401_note_pic/p351.png" alt="Drawing" style="width: 300px;"/> shows the case if $\mu = \mu_0$, the curve shift left if $\mu < \mu_0$.

    The shaded area shows the probability of obtaining $\overline X \geq \overline x$ if $\mu = \mu_0$.

-   The P-value is therefore an upper bound of the probability of obtaining the data if $H_0$ is true.

-   $P = P[D | H_0]$ if $D$ represents the statistical data, we will reject $H_0$ if it is small.

    So either:

    -   fail to reject $H_0$ at $P$ level of significance
    -   reject the $H_0$ at $P$ level of significance

    The statistic on which the $P$ is based is **test statistic**.

### Two-Tailed Test

If we are testing a hypothesis of the form $H_0: \theta = \theta_0$, we say we are performing a two-tailed test.

<img src="./ve401_note_pic/p355.png" alt="Drawing" style="width: 300px;"/> The $P$ is twice the value of one-tailed test.

