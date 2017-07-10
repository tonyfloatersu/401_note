# Elements of Probability Theory

## Joint Distribution

### Discrete Bivariate Random Variables

#### Definition

-   $S$ be a sample space
-   $\Omega \subset \mathbb{Z}^2$
-   Bivariate random variable $(X, Y): S \to \Omega$, with $f_{XY}: \Omega \to \mathbb{R}$
    -   $f_{XY}(x, y) \geq 0$ $\forall (x, y) \in \Omega$
    -   $\sum_{(x, y) \in\Omega} f_{XY}(x, y) = 1$

### Discrete Marginal Density

#### Definition

-   Let $((X, Y), f_{XY})$ be a discrete random variable
-   Marginal density $f_X(x) = \sum _ y f_{XY}(x, y)$.

### Continuous Bivariate Random Variables

#### Definition

-   $S$ be a sample space.
-   Continuous bivariate random variable $(X, Y): S\to \mathbb{R}^2$ with $f_{XY}: \mathbb{R}^2 \to \mathbb{R}$
    -   $f_{XY}(x, y) \geq 0$ $\forall (x, y) \in \mathbb{R}^2$
    -   $\begin{align}\int^\infty_{-\infty} \int^\infty_{-\infty}f_{XY}(x, y) dy dx = 1 \end{align}$
-   $\begin{align}P[(X, Y)\in\Omega] = \int \int_{\Omega} f_{XY}(x, y) d(x, y)\end{align}$

### Continuous Marginal Density

#### Definition

$\begin{align}f_X(x) = \int^\infty_{-\infty} f_{XY} (x, y) dy\end{align}$

<div style="page-break-after: always;"></div>

### Independence

#### Definition

-   $((X, Y), f_{XY})$ be bivariate random variable
-   marginal densities $f_X$ and $f_Y$
-   $\text{dom} f_{XY} = (\text{dom}f_X) \times (\text{dom}f_Y)$
-   $f_{XY} (x, y) = f_X(x) f_Y(y)$ $\forall (x, y) \in \text{dom} f_{XY}$
-   Then $(X, f_X)$ and $(Y, f_Y)$ are independent random variables.

### Conditional Densities

#### Definition

-   $((X, Y), f_{XY})$ be bivariate random variable
-   marginal densities $f_X$ and $f_Y$.
-   The conditional density for $X$ given $Y = y$ is defined to be $\begin{align}f_{X | Y} = \frac {f_{XY}(x, y)}{f_{Y(y)}}\end{align}$

### Expectation for Discrete Bivariate Random Variables

-   $((X, Y), f_{XY})$ be a discrete bivariate random variable
-   $H: \Omega \to \mathbb{R}$
-   $\begin{align}E[H\circ (X,Y)] = \sum_{(x, y)\in\Omega} H(x, y) \cdot f_{XY}(x,y)\end{align}$
-   $\begin{align}E[X] = \sum_{(x, y)\in\Omega} x \cdot f_{XY}(x,y)\end{align}$
-   $E[X+Y] = E[X]+E[Y]$

### Expectation for Continuous Bivariate Random Variables

-   $((X, Y), f_{XY})$ be a continuous bivariate random variable
-   $H: \mathbb{R}^2 \to \mathbb{R}$
-   $\begin{align} E[H\circ (X, Y)] = \int \int _{\mathbb{R}^2} H(x, y) \cdot f_{XY} (x, y) dx dy \end{align}$.
-   $\begin{align}E[X] = \int \int _{\mathbb R ^2} x\cdot f_{XY}(x, y) dx dy \end{align}$

### Conditional Expectation

#### Discrete Definition

-   $((X, Y), f_{XY})$ be a discrete bivariate random variable
-   $\begin{align}E[Y|x] := \sum_y y \cdot f_{Y|X}(y)\end{align}$

#### Continuous Definition

-   $((X, Y), f_{XY})$ be a continuous bivariate random variable
-   $\begin{align} E[Y| x] := \int _{\mathbb R} y \cdot f_{Y|X} (y) dy \end{align}$

<div style="page-break-after: always;"></div>

### Covariance

$\begin{align} Var(X + Y) &= E[((X + Y) - E[X+Y])^2] \\&= E[(X+Y)^2 - 2(X+Y)E[X+Y] + E[X+Y]^2] \\&= E[(X-E[X])^2+(Y-E[Y])^2 + 2(X-E[X])(Y-E[Y])] \\&=Var X  + Var Y + 2E[(X-E[X])(Y-E[Y])] \end{align}$

#### Definition

-   $((X, Y), f_{XY})$ be a bivariate random variable and $\mu_X = E[X]$
-   Covariance of $(X, Y)$ is $\text{Cov} (X, Y) = \sigma_{XY} = E[(X-\mu_X)(Y-\mu_Y)]$
-   We can see $\text {Cov } (X, Y) = E[XY] - E[X]E[Y]$
-   $\text{Cov}(X, X) = Var X$

#### Theorem

-   $((X, Y), f_{XY})$ be bivariate random variable
-   $\text{Cov} (X, Y) = 0$, $E[XY] = E[X] E[Y]$


### Application to the Hypergeometric Distribution

-   selecting $n$ items
-   $N$ objects
-   $r$ of which have certain property we want.
-   $X$ is the hypergeometric random variable of $r$ items drawn.

We donate $X = \sum ^n_{i=1} X_i$, where $X_i$ is a Bernoulli random variable for a single draw.

We donate the probability of success by $p_k$.

$X_k$ are neither **identically distributed** nor **independent**.

Random vector $(X_1, X_2, \cdots, X_n)$.

Since we can see from sample space $S$ that we have $N!$ permutations, then the $p_k$ probability does not depend on $k$ since all the possible permutation is listed.

Thus $\begin{align}p_k = p_1 = \frac r N\end{align}$, $\begin{align}E[X] = E[\sum^n_{k=1}X_k] = \sum^n_{k=1}E[X_k] = n\frac rN\end{align}$.

Then $\begin{align}Var X = Var (\sum^n_{k=1} X_k) = \sum ^n_{k=1} VarX_k + 2\sum_{i<j}\text{Cov}(X_i, X_j)\end{align}$

Since $\text{Cov}(X_i, X_j) = E[X_i X_j] - E[X_i] E[X_j]$

$\begin{align}E[X_i X_j] = p_{ij} := P[X_i = 1 \text{ and } X_j = 1] = \frac r N \cdot \frac {r-1} {N-1}\end{align}$

thus $\begin{align}\text{Cov}(X_i, X_j) = \frac r N \cdot \frac {r-1} {N-1} - (\frac {r}{N})^2 = -\frac 1 N \cdot \frac {r(N-r)}{N(n-1)} \end{align}$

$\begin{align}Var X = E[X^2] - E[X]^2\end{align}$, since $\begin{align}E[X_i \text{ and } X_i] = \frac r N\end{align}$, thus $\begin{align}Var X_i = \frac r N(1-\frac r N)\end{align}$.

Thus $\begin{align}Var X = n Var X_i + 2 \frac {n(n-1)}{2} \text{Cov}(X_i, X_j) = n\frac r N \frac {N-r} N \frac {N-n}{N-1}\end{align}$

<div style="page-break-after: always;"></div>

### Quantifying Dependence

#### Normalize X and Y

$\begin{align} W = \frac {X - \mu _X }{\sigma _X} \end{align}$ and $\begin{align}Z = \frac {Y - \mu_Y}{\sigma _ Y}\end{align}$

So $E[W] = E[Z] = 0$, $Var W = Var Z = 1$.

$\begin{align}\text{Cov}(W,Z) = E[WZ] = \frac {\text {Cov}(X, Y)}{\sqrt{(Var X)(Var Y)}} \end{align}$

#### Pearson Coefficient of Correlation Definition

-   $((X, Y), f_{XY})$ be bivariate random variable
-   $Var X$ and $Var Y$ are not 0
-   $\begin{align}\rho_{XY} = \frac {\text {Cov}(X, Y)}{\sqrt{(Var X)(Var Y)}} \end{align}$
-   if $\rho_{XY} = 0$, then $X$ and $Y$ are **uncorrelated**, otherwise they are **correlated**.

### Cauchy-Schwartz Inequality

-   $((X, Y), f_{XY})$ be bivariate random variable
-   correlation coefficient $\rho_{XY}$
-   $-1 \leq \rho_{XY} \leq 1$
-   $|\rho_{XY} | = 1$ iff there exist $\beta_0, \beta_1 \in \mathbb{R}, \beta_1 \neq 0$ such that $Y = \beta_0 + \beta_1 X$ almost surely.

#### Proof

-   $-1 \leq \rho _{XY} \leq 1$

    We let $E[W^2], E[Z^2] \neq 0$, then $(a W - Z)^2\geq 0$, so $0 \leq E[(aW-Z)^2] = a^2E[W^2]-2aE[WZ] + E[Z^2]$.

    Let $\begin{align}a = -\frac{E[WZ]}{E[W^2]} \end{align}$, then we get $\begin{align} -\frac{E[WZ]^2}{E[W^2]} + E[Z^2] \geq 0  \Leftrightarrow \frac {E[WZ]^2}{E[W^2]E[Z^2]} \leq 1 \end{align}$


    Let $X - \mu_X  = W$ and $Y-\mu_Y = Z$, then $\begin{align} \frac{E[(X-\mu_X)(Y-\mu_Y)]^2}{E[(X - \mu_X)^2]E[(Y-\mu_Y)^2]} = \frac{\text{Cov}(X, Y)^2}{(Var X) \cdot (Var Y)} = \rho_{XY}^2 \leq 1\end{align}$

-   $|\rho_{XY}| = 1 \Leftrightarrow Y = \beta_0 + \beta_1X$ for some $\beta_0, \beta_1 \in \mathbb R, \beta_1 \neq 0$ almost surely

    -   Suppose $Y = \beta_0 + \beta_1 X$ for some $\beta_0, \beta_1 \in \mathbb R, \beta_1 \ne 0$.

        Then $\text{Cov} (X,Y) = E[(X - E[X])(Y - E[Y])] = E[\beta_1(X - E[X])^2] = \beta_1 Var X$

        Thus $\begin{align}\rho^2_{XY} = \frac{\text{Cov}(X, \beta_0+\beta_1 X)^2}{Var(\beta_0+\beta_1X) Var X} = 1\end{align}$

    -   Let $\rho^2_{XY} = 1$, then we reverse the steps to get $\begin{align} -\frac {E[WZ]^2}{E[W^2]} +E[Z^2] = 0 \Leftrightarrow E[(aW - X)^2] = 0 \end{align}$

        thus $aW - X = 0$ almost surely, then we derive $Y = (\mu_Y-a\mu_X) + aX$ almost surely.

<div style="page-break-after: always;"></div>

### Remark on Correlation Coefficient

-   The correlation coefficient will be 0 if $X$ and $Y$ are independent, but non-independent $X, Y$ can also be $\rho_{XY} = 0$.

-   The correlation makes a statement on the expected value of the product of the normalized variables $W \cdot Z$.

    (check the $\text{Cov} (X, Y) = E[XY] - E[X]E[Y] = E[(X-\mu_X)(Y-\mu_Y)] = E[WZ]$)

    If $\rho_{XY} = 0$, then the expected value of the product is zero.

### Bivariate Normal Distribution

$\begin{align}f_{XY}(x,y) = \frac 1 {2\pi \sigma_X \sigma _Y\sqrt{1-\rho^2}} e^{-\frac 1 {2(1-\rho^2)} [(\frac {x-\mu_X}{\sigma_X})^2 - 2\rho (\frac {x-\mu_X}{\sigma_X}) (\frac {y-\mu_Y}{\sigma_Y}) + (\frac {y-\mu_Y}{\sigma_Y})^2]} \end{align}$ where $-1 < \rho < 1$.

-   $\mu_X = E[X]$
-   $\sigma_X^2 = Var X$
-   $\rho = \rho_{XY}$ is the correlation coefficient of $X$ and $Y$, $\rho = 0$ iff $X$ and $Y$ are independent.
-   $E[Y|x] = \mu_Y + \rho \frac {\sigma_Y}{\sigma_X}(x - \mu_X)$, if normalized, then $f_{XY}(x, y) = \frac 1{2\pi\sqrt{1-\rho^2}} e^{-\frac {x^2-2\rho x y + y^2}{2(1-\rho^2)}}$ and the $E[Y|x] = \rho \cdot x$.

### Transformation of Variables

#### Theorem 1

-   $((X, Y), f_{XY})$ be continuous bivariate random variable

-   $H: \mathbb R^2 \to \mathbb R ^2$ be a differentiable bijective map with inverse $H^{-1}$

-   $(U,V) = H \circ (X, Y)$ is a continuous bivariate random variable with density

    $f_{UV}(u, v) = f_{XY} \circ H^{-1} (u, v) \cdot |\det DH^{-1}(u,v)|$

    where $DH^{-1}$ is the Jacobian of $H^{-1}$.

#### Theorem 2

-   $((X, Y), f_{XY})$ be continuous bivariate random variable
-   $U=X/Y$
-   then the density $f_U$ of $U$ is given by $\begin{align}f_U(u) = \int ^\infty_{-\infty} f_{XY}(uv, v) \cdot |v| dv\end{align}$

##### Proof

-   Let $H: (X, Y) \to (U, V)$, with $H(x, y) = (x/y, y)^T$ and $H^{-1}(u, v) = (uv, v)^T$
-   $DH ^{-1}(u, v) = \begin{pmatrix} \frac {\partial x}{\partial u} & \frac{\partial x}{\partial v}\\ \frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}   \end{pmatrix} =  \begin{pmatrix} v & u\\ 0 & 1   \end{pmatrix}$
-   $|\det DH^{-1}(u,v)| = |v|$
-   Then integrate along $v$ can get the density $f_U$.