<h1 align="center">Multivariate Random Variables Part 2</h1>

### Session Preparation:
ASPE: 

Solve the [exercises from session 4](https://rbrooksdk.github.io/SMP1_25/04_Multivariate_Random_Variables/#exercises) before class.

### Session Material

[Recap Exercises](https://drive.google.com/file/d/15LXt_ODdG0qUIhZmrPiXvwHjChZpQwCH/view?usp=sharing)

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EnYOFBJCZ-hNtWAfipCS0pUB6xsNt8lOW1fDyq_l_vNqUg?e=BSqiaH)

[Session notes](https://drive.google.com/file/d/1oUHWdzQZa62bTqsmLe_eRts7OpOEhFgJ/view?usp=sharing)

Test?

Session from 20/21:

(Same as for session 4)

<iframe width="560" height="315" src="https://www.youtube.com/embed/v4rf4b2YPls?si=_VytJuuYP5z9z519" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description

Multivariate random variables are a collection of random variables that are correlated with each other. The most important elements of multivariate random variables include their mean vector, covariance matrix, and joint probability density function. The mean vector represents the average value of each variable, while the covariance matrix reflects the degree of correlation and variability among the variables. The joint probability density function specifies the probability of obtaining a particular combination of values for the variables. Understanding the key elements of multivariate random variables is crucial for performing statistical analyses, making predictions, and making decisions based on data.

#### Key Concepts
- Joint Probability Distributions
- Conditional Probability Distributions
- Conditional Expectation
- Covariance and Correlation


---

### Exercises

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>



#### Exercise 1 (only e-i)
Consider the set of points in the set \(C\):

\[
C = \{(x, y) \mid x, y \in \mathbb{Z}, x^2 + |y| \leq 2\}.
\]

Suppose that we pick a point \((X, Y)\) from this set completely at random.

1. What probability does each point have of being chosen?

2. Find the joint and marginal PMFs of \(X\) and \(Y\).

3. Find the conditional PMF of \(X\) given \(Y = 1\).

4. Are \(X\) and \(Y\) independent?

5. Find \(E[XY^2]\).

6. Find \(E[X \mid Y = 1]\).

7. Find \(\operatorname{Var}(X \mid Y = 1)\).

8. Find \(E[X \mid |Y| \leq 1]\).

9. Find \(E[X^2 \mid |Y| \leq 1]\).

??? answer
    1. 1/11

    2. Find the joint and marginal PMFs of \(X\) and \(Y\).

        \[
        \begin{aligned}
        & P_{X Y}(x, y)=\left\{\begin{array}{cc}
        \frac{1}{11} & (x, y) \in C \\
        0 & \text { otherwise }
        \end{array}\right. \\
        & P_Y(-2)=P_{X Y}(0,-2)=\frac{1}{11} \\
        & P_Y(-1)=P_{X Y}(0,-1)+P_{X Y}(-1,-1)+P_{X Y}(1,-1)=\frac{3}{11} \\
        & P_Y(0)=P_{X Y}(0,0)+P_{X Y}(1,0)+P_{X Y}(-1,0)=\frac{3}{11} \\
        & P_Y(1)=P_{X Y}(0,1)+P_{X Y}(-1,1)+P_{X Y}(1,1)=\frac{3}{11} \\
        & P_Y(2)=P_{X Y}(0,2)=\frac{1}{11} \\
        & P_X(i)=\left\{\begin{array}{cc}
        \frac{3}{11} & \text { for } i=-1,1 \\
        \frac{5}{11} & \text { for } i=0 \\
        0 & \text { otherwise }
        \end{array}\right.
        \end{aligned}
        \]

    3. Find the conditional PMF of \(X\) given \(Y = 1\).
   
        \[
        \begin{aligned}
        P_{X \mid Y}(i \mid 1) & =\frac{P_{X Y}(i, 1)}{P_Y(1)} \\
        & =\frac{\frac{1}{11}}{\frac{3}{11}}=\frac{1}{3}, \quad \text { for } i=-1,0,1 .
        \end{aligned}
        \]

    4. No

    5. \(E[XY^2]=0\).

    6. \(E[X \mid Y = 1]=0\).

    7. \(\operatorname{Var}(X \mid Y = 1)=2/3\).

    8. \(E[X \mid |Y| \leq 1]=0\).

    9.  \(E[X^2 \mid |Y| \leq 1]=2/3\).

#### Exercise 2
Consider the following PDF:

\[
f_{Y \mid X}(y) = x \cdot e^{-xy} \qquad \text{for } y > 0
\]

1. Find \(P(Y < 2 \mid X = 2)\)

2. Find \(E(Y \mid X = 2)\)

??? answer
    1. \(P(Y < 2 \mid X = 2) = 1 - e^{-4} \approx 0.98\)
    
    2. \(E(Y \mid X = 2) = \frac{1}{2}\)

#### Exercise 3
Consider two random variables \(X\) and \(Y\) with joint PMF given by:

\[
P_{X Y}(k, l) = \frac{1}{2^{k+l}}, \quad \text{for } k, l = 1, 2, 3, \ldots
\]

Find \(P\left(X^2 + Y^2 \leq 10\right)\).

??? answer
    \(P\left(X^2 + Y^2 \leq 10\right) = \frac{11}{16}\)

#### Exercise 4
Let \(X\) and \(Y\) be two jointly continuous random variables with joint PDF:

\[
f_{XY}(x, y) =
\begin{cases}
\frac{1}{2} e^{-x} + \frac{cy}{(1+x)^2}, & 0 \leq x, \quad 0 \leq y \leq 1, \\
0, & \text{otherwise}.
\end{cases}
\]

1. Find the constant \(c\).

2. Find \(P(0 \leq X \leq 1, 0 \leq Y \leq \frac{1}{2})\).

3. Find \(P(0 \leq X \leq 1)\).

??? answer
    1. \(c = 1\)
    
    2. \(P(0 \leq X \leq 1, 0 \leq Y \leq \frac{1}{2}) = \frac{5}{16}-\frac{1}{4 e}\)
    
    3. \(P(0 \leq X \leq 1) = \frac{3}{4}-\frac{1}{2 e}\)


#### Exercise 7
Let $X$ be a continuous random variable with PDF

$$
f_X(x)= \begin{cases}\frac{5}{32} x^4 & 0 \leq x \leq 2 \\ 0 & \text { otherwise }\end{cases}
$$

and let $Y=X^2$.

1. Find CDF of $Y$.
2. Find PDF of $Y$.
3. Find $E Y$.
??? answer
    1. $$F_Y(y)=\left\{\begin{array}{lc}
    0 & \text { for } y<0 \\
    \frac{1}{32} y^2 \sqrt{y} & \text { for } 0 \leq y \leq 4 \\
    1 & \text { for } y>4
    \end{array}\right.$$
    2. $$ f_Y(y)=F_Y^{\prime}(y)= \begin{cases}\frac{5}{64} y \sqrt{y} & \text { for } 0 \leq y \leq 4 \\ 0 & \text { otherwise }\end{cases}$$
    3. $$ E Y=\frac{20}{7} $$

#### Exercise 8
Consider two random variables $X$ and $Y$ with joint PMF given in the Table
<div class="center-table" markdown>

|  | $Y=0$ | $Y=1$ | $Y=2$ |
| :---: | :---: | :---: | :---: |
| $X=0$ | $\frac{1}{6}$ | $\frac{1}{4}$ | $\frac{1}{8}$ |
| $X=1$ | $\frac{1}{8}$ | $\frac{1}{6}$ | $\frac{1}{6}$ |

</div>

1. Find $\operatorname{Cov}(X, Y)$
2. Find $\rho(X, Y)$
??? answer
    1. \(\operatorname{Cov}(X, Y)=\frac{1}{24}\)
    2. \(\rho(X, Y)\approx 0.11\)

#### Exercise 9
Let $X$ and $Y$ be two independent $N(0,1)$ random variables and

$$
\begin{aligned}
& Z=11-X+X^2 Y \\
& W=3-Y
\end{aligned}
$$


Find $\operatorname{Cov}(Z, W)$.

??? answer
    $$\operatorname{Cov}(Z, W)=-1$$

#### Exercise 10
Let $X$ denote the stochastic variable with the following PDF:

$$
f_X(x)= \begin{cases}\frac{3}{8} x^2 & 0<x<2 \\ 0 & \text { otherwise }\end{cases}
$$

1. Find $P(X>3 / 4)$ and $P(X<3 / 4)$.
2. Find $E[(X+2) / 3]$ and $E\left[X^2\right]$
3. Let $Z=e^{2 X}$ and find the probability density function of $Z$ for all $z \in \mathbb{R}$.

Let $Y$ denote the stochastic variable that is independent to $X$ and has the distribution as $X$, i.e. $Y$ has the following PDF:

$$
f_Y(y)= \begin{cases}\frac{3}{8} y^2 & 0<y<2 \\ 0 & \text { otherwise }\end{cases}
$$

4. Find $\operatorname{Cov}(2 X+3 Y, X-4 Y+9)$.
5. Find $P(X \cdot Y<1)$.