<h1 align="center">Continuous Random Variables</h1>

### Session Preparation:
ASPE: 4 (not 4.8-4.11)

Solve the [exercises from session 2](https://rbrooksdk.github.io/SMP1_25/02_Discrete_Random_Variables/#exercises) before class.

Today you will need to brush up on your basic calculus skills as this will not be recapped in depth. It seems that Khan Academy has some nice tutorials on integrals that you may want to check out:

- [Tutorial 1](https://www.khanacademy.org/math/ap-calculus-ab/ab-integration-new/ab-6-7/v/connecting-the-first-and-second-fundamental-theorems-of-calculus)
- [Tutorial 2](https://www.khanacademy.org/math/ap-calculus-ab/ab-integration-new/ab-6-8b/v/antiderivative-of-x-1)
- [Tutorial 3](https://www.khanacademy.org/math/ap-calculus-ab/ab-integration-new/ab-6-8c/v/reverse-power-rule-for-definite-integrals)


### Session Material

[Recap notes]()

[Session notes Part 1]()

[Session notes Part 2]()

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/Ev_P59eY9qJOiDMwGkdri9ABxzovHXJiHdLP432519F7vQ?e=gwTShz)

Session from 20/21:

<iframe width="560" height="315" src="https://www.youtube.com/embed/KKSraC6Kmsc?si=it-tBiiATJrWQ5Yj" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description

Continuous random variables are a type of random variable that can take on an infinite number of values within a given range. The most important elements of continuous random variables are the probability density function, the cumulative distribution function, and the expected value. The probability density function provides the probability that a continuous random variable will take on a value within a given range, while the cumulative distribution function gives the probability that the variable will take on a value less than or equal to a given value. The expected value, or mean, of a continuous random variable is calculated by integrating the product of the variable and its probability density function over the entire range of possible values.

It is also important that you think about the relationship between the discrete case and the continuous case, and how this transfers to the relationship between sums and integrals.

#### Key Concepts
- Derivatives, integrals, antiderivatives
- General properties of continuous random variables
- The uniform distribution
- The probability density function
- The cumulative distribution function
- The normal distribution
- The exponential distribution

---

### Exercises
Full solutions to the exercises can be found in the [general resource folder](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/Egbdbeb9oy1Oqk8hReXf2-wBibryPlLiVj2ujGdsvH5--w?e=liO02A)

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>

#### Exercise 1 (Exam 2014.1)
Let \(X\) denote a continuous stochastic variable with the following probability density function:

\[
    f(x) =
    \begin{cases}
    c x^4 & \text{for } -1 \leq x \leq 1, \\
    0 & \text{otherwise,}
    \end{cases}
\]

where \(c\) is a constant.

1. Show that the cumulative probability function of \(X\) is:

    \[
    F(x) =
    \begin{cases}
    0 & \text{for } x < -1, \\
    \frac{1}{5} c\left(x^5 + 1\right) & \text{for } -1 \leq x \leq 1, \\
    1 & \text{for } x > 1.
    \end{cases}
    \]

2. Determine the constant \(c\) and restate both the probability density function and the cumulative probability function using the actual value of \(c\).

3. Compute \(P\left(-\frac{1}{2} < X < \frac{1}{2}\right)\) and \(P(X > 0)\).

4. Find the expected value and variance of \(X\).

??? answer
    1. Can be shown either by integrating the probability density function or by differentiating the cumulative probability function.
    2. \(c = \frac{5}{3}\)
    3. \(P\left(-\frac{1}{2} < X < \frac{1}{2}\right) = \frac{1}{32} = 0.0315\) and \(P(X > 0) = \frac{1}{2} = 0.5\)
    4. \(E[X] = 0\) and \(VAR(X) = \frac{5}{7}\)

#### Exercise 2 (Exam 2014.3 (not d+e))
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

#### Exercise 3 (Exam 2018.1)
Let \(X\) denote a continuous stochastic variable with the following density function

$$
f(x)= \begin{cases}c\left(1-x^2\right) & \text { for }-1<x<1 \\ 0 & \text { otherwise }\end{cases}
$$

1. Determine the value of \(c\) and state the cumulative distribution function of \(X\).
2. Determine \(P\left(X \leq \frac{1}{2}\right)\) and \(P\left(X \leq-\frac{1}{4}\right)\)
3. Determine the expected value and the variance of \(X\).

??? answer
    a. \(c = \frac{3}{4}\) and \(F(x) = \begin{cases}0 & \text { for } x<-1 \\ \frac{3}{4}\left(x-\frac{x^3}{3}\right) + \frac{1}{2} & \text { for }-1 \leq x \leq 1 \\ 1 & \text { for } x>1\end{cases}\)

    b. \(P\left(X \leq \frac{1}{2}\right) = 0.8438\) and \(P\left(X \leq-\frac{1}{4}\right) = 0.3164\)

    c. \(E[X] = 0\) and \(VAR(X) = 0.2\)



#### Exercise 4 (Re-exam 2018.1)
Compute the expected value, \(E(X)\), if \(X\) has a density function as follows:

1. \(f(x)= \begin{cases}\frac{1}{4} x e^{-\frac{x}{2}} & x>0 \\ 0 & \text { otherwise }\end{cases}\)
2. \(f(x)= \begin{cases}5 x^{-2} & x>5 \\ 0 & \text { otherwise }\end{cases}\)

    The density function of \(X\) is given by

    $$
    f(x)= \begin{cases}a+b x^2 & 0 \leq x \leq 1 \\ 0 & \text { otherwise }\end{cases}
    $$

3. If \(E(X)=\frac{3}{5}\), find \(a\) and \(b\).

??? answer
    1. \(E(X) = 4\)
    2. \(E(X) = \infty \)
    3. \(a = \frac{3}{5}\) and \(b = \frac{6}{5}\)

#### Exercise 5 (Exam 2020.1)
The length of time \(X\) (in hours), needed by students in the SMP course to complete the three-hour exam is a continuous random variable with the following density function:

\[
f(x) =
\begin{cases}
q\left(x^2 + x\right) & \text{if } 0 \leq x \leq 3, \\
0 & \text{else}.
\end{cases}
\]

1. Find the value of \(q\) that makes \(f(x)\) a probability density function.

2. Find the cumulative distribution function.

3. Find the probability that a student will complete the exam in:
    - (i) Less than an hour.
    - (ii) Between one and two hours.
    - (iii) More than two hours.
    - (iv) During the final ten minutes of the exam.

4. Find the mean time needed to complete the three-hour SMP exam.

5. Find the variance and standard deviation of \(X\).

??? answer
    1. \(q = \frac{2}{27} \approx 0.0741\)
    2. \(F(x) = \begin{cases}0 & \text{if } x < 0, \\ \frac{2 x^3}{81}+\frac{x^2}{27} & \text{if } 0 \leq x \leq 3, \\ 1 & \text{if } x > 3.\end{cases}\)
    3. (i) \(P(X<1)=5 / 81=0.0617\), (ii) \(P(1<X<2)=23 / 81=0.284\), (iii) \(P(X>2)=53 / 81=0.6543\), (iv) \(P(X>17 / 6)=0.1411\)
    4. \(E[X] = 13/6 =2.1667 \text { hours } \)
    5. \(\operatorname{Var}(X)=0.4056\) hours \(^2\) and \(\mathrm{SD}(X)=0.6368\) hours

