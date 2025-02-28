<h1 align="center">Normal and Exponential Distributions  and Multivariate Random Variables</h1>

### Session Preparation:
ASPE: 5 (not 5.5-5.8)

Solve the [exercises from session 3](https://rbrooksdk.github.io/SMP1_25/03_Continuous_Random_Variables/#exercises) before class.

### Session Material

[Recap Notes](https://drive.google.com/file/d/11-lAHXLQO_PRv2xqHwjoZv66-PY9X-9x/view?usp=sharing)

[CRVs Part 2 Notes](https://drive.google.com/file/d/1fBRTsno83ezsVh-VThX5j31NeXG-n_SL/view?usp=sharing)

[Session notes](https://drive.google.com/file/d/1oUHWdzQZa62bTqsmLe_eRts7OpOEhFgJ/view?usp=sharing)

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

2. Find \(E[X]\), \(E[Y]\), and \(E[XY]\). Hint: It works in more or less the same way as for one variable.

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
        \frac{1}{12} & \text{for } y=5, \\
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
Let the simultaneous probability mass function for the two discrete random variables \(X\) and \(Y\) be given by the table:

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
        & f_X(x)= \begin{cases}\frac{4}{10} & x=4 \\
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
Let $X \sim N(3,9)$.

1. Find $P(X>0)$.
2. Find $P(-3<X<8)$.
3. Find $P(X>5 | X>3)$.

??? answer
    1. \(P(X>0)=\Phi(1) \approx 0.8413\)
    2. \(P(-3<X<8)=\Phi\left(\frac{5}{3}\right)-\Phi(-2) \approx 0.9295\).
    3. \(P(X>5 \mid X>3)=2 \times\left(1-\Phi\left(\frac{2}{3}\right)\right) \approx 0.5050\)

#### Exercise 4
Let $X \sim N(3,9)$ and $Y=5-X$.

1. Find $P(X>2)$.
2. Find $P(-1<Y<3)$.
3. Find $P(X>4 |Y<2)$.

??? answer
    1. \(P(X>2)=1-\Phi\left(\frac{1}{3}\right) \approx 0.6306\)
    2. \(P(-1<Y<3)=\Phi\left(\frac{1}{3}\right)-\Phi(-1) \approx 0.4719 \).
    3. \(P(X>4 \mid Y<2)=2\left(1-\Phi\left(\frac{1}{3}\right)\right) \approx 0.7389 .\)


#### Exercise 5 (Exam 2014.3 (not a-c))
A central database server receives, on the average, 25 requests per second from its clients. Assuming that requests received by a database follow a Poisson distribution

<ol start="1">
    <li>What is the probability that the server will receive no requests in a 10-millisecond interval?</li>
    <li>What is the probability that the server will receive more than 2 requests in a 10-millisecond interval?</li>
    <li>What is the probability that the server will receive between 2 and 4 (both included) requests in a 20-millisecond interval?</li>
</ol>

Let T be the time in seconds between requests.

<ol start="4">
    <li>What is the probability that less than or equal to 10 milliseconds will elapse between job requests?</li>
    <li>What is the probability that more than 100 milliseconds will elapse between requests?</li>
</ol>


??? answer
    1. \(P(X=0) = 0.7788\)
    2. \(P(X>2) = 0.0022\)
    3. \(P(2 \leq X \leq 4) = 0.09\)
    4. \(P(T \leq 0.01) = 0.2212\)
    5. \(P(T > 0.1) = 0.0821\)

#### Exercise 6 (only a-d)
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