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

-   $((X, Y), f_{XY})$ be a bivariate random variable
-   $\mu_X = E[X]$
-   Covariance of $(X, Y)$ is $\text{Cov} (X, Y) = \sigma_{XY} = E[(X-\mu_X)(Y-\mu_Y)]$
-   We can see $\text {Cov } (X, Y) = E[XY] - E[X]E[Y]$
-   $\text{Cov}(X, X) = Var X$

#### Theorem

-   $((X, Y), f_{XY})$ be bivariate random variable
-   $\text{Cov} (X, Y) = 0$, $E[XY] = E[X] E[Y]$

