# Elements of Probability Theory

## Intro to Probability and Counting

-   **tree diagram** helps to count outcomes

-   there are $\frac{n!}{n_1! ... n_k!}$ ways of partitioning $A$ into $k$ disjoint subsets $A_i$ with union as $A$, where each $a_i$ as $n_i$ elements. This is **permutation of $k$ indistinguishable objects from $A$**.

-   **sample space** is a set $S$ with each outcome corresponds to exactly one element in $S$.

-   **event** is any subset $A$ of a sample space $S$.

-   **mutually exclusive** if events $A_1$, $A_2$: $A_1 \cap A_2 = \emptyset$.

-   In the experiment, the **average** outcome of an experiment is not necessarily **the most likely** outcome.

    e.g: toss a fail coin 4 times, then in the 16 outcomes, 2-2 is 6 times while 1-3 is 8 times.

### Axiomatic Definition of Probability

#### $\sigma$-field $F$

Let $S$ be a non-empty set. $\sigma$-field $F$ on $S$ is **a family of subsets of $S$**:

-   $\emptyset \in F$
-   $A \in F \Rightarrow S \backslash A \in F$
-   $A_1, A_2 ... \in F \Rightarrow \cup_k A_k \in F$

So here are some examples:

-   If $S$ is finite, then $F = P(S)$ (power set of S) can be used. ($F$ here is $\sigma$-field.)
-   $\forall S$, the smallest possible $\sigma$-field $F = {\emptyset, S}$.
-   **Borel Sets** $B(I)$ is on an interval $I \subset \mathbb{R}$, the smallest $\sigma$-family containing all subintervals of $I$.


### Probability Measure

Let $S$ be a sample space and $F(S)$ a $\sigma$-field on $S$.

$$P: F \rightarrow [0, 1], A \mapsto P[A]$$ is called a **probability measure** on $S$ if

-   $P[S] = 1$

-   If all $\{A_k\} \subset F$ with mutually exclusive ($A_j \cap A_k =\emptyset, j \neq k$)

    $P[\cup_kA_k] = \sum_kP[A_k]$

the triple $(S, F, P)$ is a **probability space**.

### Conditional Probability

$P[A_1|A_2] = \frac{P[A_1 \cap A_2]}{P[A_2]}$ with $P[A_2] \neq 0$.

<div style="page-break-after: always;"></div>

### Another Child Example

At a gathering of parents of Boy Scouts, you meet a mother with her son. She says “Actually, I also have a second child.”

-   So probability that the other child is a girl?

    Sample Space $\{(b,b), (b,g), (g,b)\}$, so $P[\text{other child girl}] = \frac{2}{3}$.

-   She then tells you, “My son here is my older child.” What is the probability that the other child is a girl?

    $P[\text{other child is girl } | \text{ the older is boy}] = \frac{1}{2}$.

### Independence of Events

$A, B$ are **independent** if $P[A\cap B] = P[A]\cdot P[B]$.

Thus $P[A |B] = P[A]$ if $P[B] \neq 0$.

### Birthday Example

How many people should a group have so that there is greater than even chance of two people in the group having the same birthday?

Consider the first person, then we add a second person, there is $\frac{364}{365}$ possibility for them to share different birthday.

Keep adding, we see the possibility of sharing different birthday is $\frac{364! / (365-n)!}{365^{n-1}} (n \geq 2)$.

So when $n=23$ the possibility is lower than 0.5, which means when 23 people group, the possibility of sharing same birthday is greater than 0.5.

### Total Probability

$P[B] = \sum P[B | A_j] \cdot P[A_j]$.

### Bayes’s Theorem

Let $A_1, A_2, ..., A_n \subset S$ be a set of mutually exclusive events with $\cup A_i = S$.

Let $B \subset S$ be any event such that $P[B] \neq 0$.

Thus $P[A_k | B] = \frac{P[B \cap A_k]}{P[B]} = \frac{P[B | A_k] \cdot P[A_k]}{\sum_{j=1}^{n} P[B | A_j] \cdot P[A_j]}$.

<div style="page-break-after: always;"></div>

### Partner Problem

$n$ candidates to choose, there is a $x_k \in \{1, ... n\}$ for the rank of $k^{th}$ partner, but this is unknown to you. You can evaluate with a *relative rank* $y_k \in \{1, ... n\}$.

The problem is: what is the best strategy for finding the most suitable partner with $x_k = 1$.

**Optimal Strategy**: evaluate and reject $n-1$ partners then choose the first partner superior to all previous ones.

So $y_k = 1$ is the first partner chosen given $k \geq n$ chosen.

So for $r = 2, .. n$, donate $\sigma_r$ for strategy and $p_r$ for probability under strategy $\sigma_r$.

The problem changes to finding an $r$ to maximize $p_r$.

Let $B_k$ be the event $\{x_k = 1\}$ and donate $W$ be the event of getting best partner.

Since the partners are in random order, then $P[B_k] = \frac{1}{n}$.

**Select no partner probability**: if $x_m =1$ for $m < r$, then the probability is $p=\frac{r-1}{n}$.

**Other normal cases**: under strategy $\sigma_r$ we have $P[W | B_m] = 0$ for $m < r$.

So $p_r = \frac{1}{n} \sum^n_{m=r} P[W|B_m]$.

​:idea: suppose $1 < r \leq m$, $x_m = 1$.

​:idea: the strategy $\sigma_r$ leads to winning if there is no $y_k=1$ for $r \leq k < m$.

​:idea: i.e., the minimum of $(x_1, ..., x_{r-1}, x_r, ..., x_{m-1})$ occurs only in $1 \leq k \leq r-1$.

Thus the possibility $P[W|B_m] = \frac{r-1}{m-1}$.

Hence, $p_r = \frac{1}{n} \sum^n_{m=r} \frac{r-1}{m-1} = \frac{r-1}{n} \sum^n_{m=r}\frac{1}{m-1}$.

Apply approximation $\sum^n_{k=1} \frac{1}{k} = ln(n)$.

Let $x = \frac {r}{n}$, we get $p_r = (x - \frac{1}{n})\cdot (\sum^n_{m=2} \frac{1}{m-1} - \sum^{r-1}_{m=2}\frac{1}{m-1})\\\text{ }= (x-\frac{1}{n}) \cdot (ln(n-1) - ln(r-2)) = -x\cdot ln(x)$

So when $x = \frac{r}{n} = x_{max} = 37\%$, optimal strategy arrive.

And the total situation is this:

-   $37\%$ for best partner
-   $37\%$ for rejecting all partners ($1< m < r$)
-   $26\%$ for finding inferior choice

<div style="page-break-after: always;"></div>

### The Monty Hall Paradox

You are participating in a game show to win 10,000,000 RMB. The game master [Monty Hall] presents you with three closed doors. Behind one of the doors is the prize, behind the other two doors there is simply a goat. If you open the correct door, you will receive the money, if you open one of the other two doors you will get a goat.

Before opening any of the three doors, you can announce which door you intend to open. Obviously, at least one of the other two doors does not hide the money. The game master opens this (empty) door. You are then given the option of either

-   sticking with your choice or
-   switching to the other closed door.

You have chosen door 1. Then door 3 is shown to harbor a goat. To win the money, should you switch to door 2?

**Solution:**

Suppose the doors are denoted $A$, $B$ and $C$ and denote by the same letter $X$ the event “prize is behind door $X$” where $X = A,B, C$.

We denote the event “host opens door $B$” by $B^*$.

Suppose that door $A$ is initially selected and that the host opens door $B$.

Then $P[A | B^*] =\frac{P[B^*|A] \cdot P[A]}{P[B^*|A] \cdot P[A] + P[B^*|B] \cdot P[B] + P[B^*|C]\cdot P[C]}$.

Since $P[A]=P[B]=P[C] = \frac{1}{3}$, so $P[A | B^*] =\frac{P[B^*|A]}{P[B^*|A] + P[B^*|B]+ P[B^*|C]}$.

-   For $P[B^*|A]$, if you choose $A$, the master can choose either $B$ or $C$.
-   For $P[B^*|B]$, this is impossible since master will not open $B$ if price is after $B$.
-   For $P[B^*|C]$, chosen $A$ and price after $C$, so only $B$ can be opened.

So $P[A|B^*]=\frac{1}{3}$.

