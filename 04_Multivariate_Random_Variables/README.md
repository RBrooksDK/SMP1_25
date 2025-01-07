<h1 align="center">Multivariate Random Variables</h1>

### Session Preparation:
ASPE: 5 (not 5.5-5.8)

Solve the [exercises from session 3](https://rbrooksdk.github.io/SMP1_25/03_Continuous_Random_Variables/#exercises) before class.

### Session Material

[Recap Notes]()

[CRVs Part 2 Notes]()

[Session notes]()

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EoKqqy67NdBBk7Qnug21TH4BXHHtg2jlNNSF45_H9n7feg?e=3dBknY)

Session from 20/21:

<iframe width="560" height="315" src="https://www.youtube.com/embed/v4rf4b2YPls?si=_VytJuuYP5z9z519" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description

This is arguably the most difficult of all the topics.

Multivariate random variables are a collection of random variables that are correlated with each other. The most important elements of multivariate random variables include their mean vector, covariance matrix, and joint probability density function. The mean vector represents the average value of each variable, while the covariance matrix reflects the degree of correlation and variability among the variables. The joint probability density function specifies the probability of obtaining a particular combination of values for the variables. Understanding the key elements of multivariate random variables is crucial for performing statistical analyses, making predictions, and making decisions based on data.

#### Key Concepts
- Joint Probability Distributions
- Conditional Probability Distributions
- Conditional Expectation
- Covariance and Correlation

---
### Exercises
Full solutions to the exercises can be found in [Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EthiTapbBz1JrNRDVKsHTnkB2LPmmbKwlY22zvyaCJMI9Q?e=0ggVfo).

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>

#### Exercise 1
Let the simultaneous probability mass function (also called simultaneous probability density function or pdf) for the two discrete random variables \(X\) and \(Y\) be given by the table:

<div class="center-table" markdown>

| \(y \backslash x\) | 1           | 2           | 3           |
|---------------------|-------------|-------------|-------------|
| 5                   | \(\frac{1}{12}\) | 0           | 0           |
| 6                   | \(\frac{2}{12}\) | 0           | \(\frac{2}{12}\) |
| 7                   | \(\frac{2}{12}\) | \(\frac{1}{12}\) | \(\frac{2}{12}\) |
| 8                   | 0           | \(\frac{2}{12}\) | 0           |

</div>

1. Find the marginal PMFs of \(X\) and \(Y\).

2. Find \(E[X]\), \(E[Y]\), and \(E[XY]\).

3. Specify whether \(X\) and \(Y\) are independent.

4. Find \(f_{X \mid Y}(x \mid y=6)\).

??? answer
    1. The marginal PMFs of \(X\) and \(Y\) are:
    
        \[
        f_X(x) = 
        \begin{cases}
        \frac{5}{12} & \text{for } x=1, \\
        \frac{1}{4} & \text{for } x=2, \\
        \frac{1}{3} & \text{for } x=3, \\
        0 & \text{otherwise,}
        \end{cases}
        \]
        
        \[
        f_Y(y) = 
        \begin{cases}
        \frac{5}{12} & \text{for } y=5, \\
        \frac{4}{12} & \text{for } y=6, \\
        \frac{5}{12} & \text{for } y=7, \\
        \frac{2}{12} & \text{for } y=8, \\
        0 & \text{otherwise.}
        \end{cases}
        \]
    
    2. \(\mathrm{EX}=1.92, \mathrm{EY}=6.67, \mathrm{E}[\mathrm{XY}]=12.92\)
    
    3. Not
    
    4. \(f_{X \mid Y}(1 \mid 6)=0.5, \quad f_{X \mid Y}(2 \mid 6)=0, \quad f_{X \mid Y}(3 \mid 6)=0.5\)

#### Exercise 2
Let the simultaneous probability mass function (also called simultaneous probability density function or pdf) for the two discrete random variables \(X\) and \(Y\) be given by the table:

<div class="center-table" markdown>

| \(y \backslash x\) | 4           | 5           | 7           |
|---------------------|-------------|-------------|-------------|
| -3                 | \(k\)       | 0           | 0           |
| -1                 | \(\frac{2}{10}\) | 0           | \(k\)       |
| 0                  | \(\frac{1}{10}\) | 0           | \(\frac{4}{10}\) |
| 5                  | 0           | \(k\)       | 0           |

</div>

1. What is the value of \(k\)?

2. What are the marginal PMFs?

3. Find:
   
    \(E[X] =\)
    
    \(E[Y] =\)
    
    \(E[Y \cdot X] =\)
    
    \(E[X^2] =\)
    
    \(E[Y^2] =\)
    
    \(P(Y < 0) =\)
    
    \(P(X = 5, Y > 0) =\)
    
    \(P(X < 6, Y < 0) =\)
    
    \(\text{Var}(X) =\)

??? answer
    1. \(k = \frac{1}{10}\)

    2. The marginal PMFs are:
   
        \[
        \begin{aligned}
        & f_X(x)= \begin{cases}\frac{4}{5} & x=4 \\
        \frac{1}{10} & x=5 \\
        \frac{1}{2} & x=7\end{cases} \\
        & f_Y(y)= \begin{cases}\frac{1}{10} & y=-3 \\
        \frac{3}{10} & y=-1 \\
        \frac{1}{2} & y=0 \\
        \frac{1}{10} & y=5\end{cases}
        \end{aligned}
        \]
    3. Find:

        \(E[X] =5.6\)
        
        \(E[Y] =-0.1\)
        
        \(E[Y \cdot X] =-0.2\)
        
        \(E[X^2] =33.4\)
        
        \(E[Y^2] =3.7\)
        
        \(P(Y < 0) =0.4\)
        
        \(P(X = 5, Y > 0) =0.1\)
        
        \(P(X < 6, Y < 0) =0.3\)
        
        \(\text{Var}(X) =2.04\)

#### Exercise 3
Consider the following PDF:

\[
f_{Y \mid X}(y) = x \cdot e^{-xy} \qquad \text{for } y > 0
\]

1. Find \(P(Y < 2 \mid X = 2)\)

2. Find \(E(Y \mid X = 2)\)

??? answer
    1. \(P(Y < 2 \mid X = 2) = 1 - e^{-4} \approx 0.98\)
    
    2. \(E(Y \mid X = 2) = \frac{1}{2}\)

#### Exercise 4
Consider two random variables \(X\) and \(Y\) with joint PMF given by:

\[
P_{X Y}(k, l) = \frac{1}{2^{k+l}}, \quad \text{for } k, l = 1, 2, 3, \ldots
\]

Find \(P\left(X^2 + Y^2 \leq 10\right)\).

??? answer
    \(P\left(X^2 + Y^2 \leq 10\right) = \frac{11}{16}\)

#### Exercise 5
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

#### Exercise 6
Let \(X\) and \(Y\) be two jointly continuous random variables with joint PDF:

\[
f_{XY}(x, y) =
\begin{cases}
e^{-xy}, & 1 \leq x \leq e, \quad y > 0, \\
0, & \text{otherwise}.
\end{cases}
\]

1. Find the marginal PDFs, \(f_X(x)\) and \(f_Y(y)\).

2. Write an integral to compute \(P(0 \leq Y \leq 1, 1 \leq X \leq \sqrt{e})\).

??? answer
    1. The marginal PDFs are:
       
        \[
        \begin{aligned}
        & f_X(x)= \begin{cases}\frac{1}{x} & 1 \leq x \leq e \\
        0 & \text { otherwise }\end{cases} \\
        & f_Y(y)= \begin{cases}\frac{1}{y}\left(e^{-y}-e^{-e y}\right) & y>0 \\
        0 & \text { otherwise }\end{cases}
        \end{aligned}
        \]

    2. \[P(0 \leq Y \leq 1,1 \leq X \leq \sqrt{e})=\int_1^{\sqrt{e}} \frac{1}{x}-\frac{1}{x} e^{-x} d x\]

#### Exercise 7
Let \(X\) and \(Y\) be two jointly continuous random variables with joint PDF:

\[
f_{XY}(x, y) =
\begin{cases}
\frac{1}{4}x^2 + \frac{1}{6}y, & -1 \leq x \leq 1, \quad 0 \leq y \leq 2, \\
0, & \text{otherwise}.
\end{cases}
\]

1. Find the marginal PDFs, \(f_X(x)\) and \(f_Y(y)\).

2. Find \(P(X > 0, Y < 1)\).

3. Find \(P(X > 0 \text{ or } Y < 1)\).

4. Find \(P(X > 0 \mid Y < 1)\).

5. Find \(P(X + Y > 0)\).

??? answer
    1. The marginal PDFs, \(f_X(x)\) and \(f_Y(y)\).
   
        \[
        \begin{aligned}
        & f_X(x)=\left\{\begin{array}{lc}
        \frac{1}{2} x^2+\frac{1}{3} & -1 \leq x \leq 1 \\
        0 & \text { otherwise }
        \end{array}\right. \\
        & f_Y(y)= \begin{cases}\frac{1}{6}+\frac{1}{3} y & 0 \leq y \leq 2 \\
        0 & \text { otherwise }\end{cases}
        \end{aligned}
        \]

    2. \(P(X > 0, Y < 1)\) = 1/6.
    3. \(P(X > 0 \text{ or } Y < 1)=2/3\).
    4. \(P(X > 0 \mid Y < 1)=1/2\).
    5. \(P(X + Y > 0)=131/144\).