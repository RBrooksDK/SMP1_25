<h1 align="center">Introduction + Probability + Stochastic Variables</h1>

### Session Preparation:
ASPE: 1-2

There are no exercises to be solved before class, since it is the first class. However, it is recommended to go through the material and make sure you understand the concepts.

Also, check out the [prerequisites](https://rbrooksdk.github.io/SMP1_25/00_Important_Recap/) for the course.

### Session Material

[Session Notes]()

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EuOeq6E9sg9Jjf5n_qCeM80B4uonPufDX4RnR0nFz3EdMg?e=dRNi7T)

Make sure you are acquainted with common [Series, Approximations, and Identities](https://lpsa.swarthmore.edu/BackGround/UsefulSeries/)

Session from 20/21:

<iframe width="560" height="315" src="https://www.youtube.com/embed/F3bB33pqjLw?si=G7eN7FQnrZj1XLWN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description
In this session, we will look at the foundational principles of statistics and probability theory, starting with an understanding of why these fields are essential for analysing data and making predictions. We will discuss the distinction between samples and populations, along with key measures and scales of measurement. The session will introduce random experiments and the foundational concepts of probabilities.

Building on this, we will review key concepts in probability, including types of probability, conditional probability, and conditional independence. Finally, we introduce the concept of a random variable.

#### Key Concepts
- Importance of Statistics and Probability Theory
- Samples vs. Populations
- Measures and Scales of Measurement
- Random Experiments and Probabilities
- Types of Probability
- Conditional Probability
- Conditional Independence
- Expectation and Variance
- Independent Random Variables
- Functions of Random Variables


---

### Exercises
Full solutions to the Exam case exercises (8-10) can be found in the [general resource folder](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/Egbdbeb9oy1Oqk8hReXf2-wBibryPlLiVj2ujGdsvH5--w?e=liO02A)

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>

#### Exercise 1
Heart failures are due to either natural occurrences
(87%) or outside factors (13%). Outside factors are related to
induced substances (73%) or foreign objects (27%). Natural
occurrences are caused by arterial blockage (56%), disease (27%),
and infection (e.g., staph infection) (17%).

1. Determine the probability that a failure is due to an induced substance.

2. Determine the probability that a failure is due to disease or infection.



??? answer

    1. \(P(\text{induced substance}) = 0.13 \times 0.73 = 0.0949\)

    2. $P(\text{disease or infection}) = 0.87\times (0.27+0.17) = 0.3828$

#### Exercise 2
Computer keyboard failures are due to faulty electrical connects (12%) or mechanical defects (88%). Mechanical defects are related to loose keys (27%) or improper assembly (73%). Electrical connect defects are caused by defective wires (35%), improper connections (13%), or poorly welded wires (52%).

1. Find the probability that a failure is due to loose keys.

2. Find the probability that a failure is due to improperly connected or poorly welded wires.

??? answer

    1. \(P(\text{loose keys}) = 0.88 \times 0.27 = 0.2376\)

    2. \(P(\text{improperly connected or poorly welded wires}) = 0.12 \times (0.13 + 0.52) = 0.078\)

#### Exercise 3
Two teams \(A\) and \(B\) play a football match, and we are interested in the winner. The sample space can be defined as:  

\[
S = \{a, b, d\}
\]  

where \(a\) shows the outcome that \(A\) wins, \(b\) shows the outcome that \(B\) wins, and \(d\) shows the outcome that they draw. Suppose that we know that:

* The probability that \(A\) wins is \(P(a) = P(\{a\}) = 0.5\).  
* The probability of a draw is \(P(d) = P(\{d\}) = 0.25\).

Based on this,

1. Find the probability that \(B\) wins.

2. Find the probability that \(B\) wins or a draw occurs.

??? answer

    1. \(P(b) = 1 - P(a) - P(d) = 1 - 0.5 - 0.25 = 0.25\)

    2. \(P(b \cup d) = P(b) + P(d) = 0.25 + 0.25 = 0.5\)

#### Exercise 4
Let \(A\) and \(B\) be two events such that:  

\[
    P(A) = 0.4, \quad P(B) = 0.7, \quad P(A \cup B) = 0.9
\]

1. Find \(P(A \cap B)\).

2. Find \(P(A^c \cap B)\).

3. Find \(P(A - B)\).

4. Find \(P(A^c - B)\).

5. Find \(P(A^c \cup B)\).

6. Find \(P(A \cap (B \cup A^c))\).

??? answer

    1. \(P(A \cap B) = P(A) + P(B) - P(A \cup B) = 0.4 + 0.7 - 0.9 = 0.2\)

    2. \(P(A^c \cap B) = P(B) - P(A \cap B) = 0.7 - 0.2 = 0.5\)

    3. \(P(A - B) = P(A) - P(A \cap B) = 0.4 - 0.2 = 0.2\)

    4. \(P(A^c - B) = 1 - P(A \cup B) = 1 - 0.9 = 0.1\)

    5. \(P(A^c \cup B) = 1 - P(A - B) = 1 - 0.2 = 0.8\)

    6. \(P(A \cap (B \cup A^c)) = P(A \cap B) = 0.2\)

#### Exercise 5
Consider a random experiment with a sample space: 

\[
S = \{1, 2, 3, \cdots\}.
\]  

Suppose that we know:  

\[
P(k) = P(\{k\}) = \frac{c}{3^k} \quad \textrm{for} \quad k = 1, 2, \cdots
\]  

where \(c\) is a constant number.

1. Find \(c\).

2. Find \(P(\{2, 4, 6\})\).

3. Find \(P(\{3, 4, 5, \cdots\})\).

??? answer

    1. To find \(c\), use the fact that the sum of all probabilities must equal 1:
      
        \[
        \sum_{k=1}^\infty P(k) = \sum_{k=1}^\infty \frac{c}{3^k} = 1.
        \]

        This is a geometric series with the first term \(\frac{c}{3}\) and ratio \(\frac{1}{3}\):
       
        \[
        \sum_{k=1}^\infty \frac{c}{3^k} = \frac{c}{3} \cdot \frac{1}{1 - \frac{1}{3}} = \frac{c}{3} \cdot \frac{3}{2} = \frac{c}{2}.$
        \]

        Therefore, \(\frac{c}{2} = 1 \implies c = 2\).

    2. \(P(\{2, 4, 6\})\):
       
        \[
        P(\{2, 4, 6\}) = P(2) + P(4) + P(6) = \frac{2}{3^2} + \frac{2}{3^4} + \frac{2}{3^6}.
        \]
       
        Compute each term:
       
        $$
        P(\{2, 4, 6\}) = \frac{2}{9} + \frac{2}{81} + \frac{2}{729} = \frac{162 + 18 + 2}{729} = \frac{182}{729} \approx 0.25.
        $$

    3. \(P(\{3, 4, 5, \cdots\})\):
       
        $$
        P(\{3, 4, 5, \cdots\}) = \sum_{k=3}^\infty P(k) = \sum_{k=3}^\infty \frac{2}{3^k}.
        $$
        
        This is a geometric series starting at \(k=3\) with the first term \(\frac{2}{3^3} = \frac{2}{27}\) and ratio \(\frac{1}{3}\):
        
        $$
        P(\{3, 4, 5, \cdots\}) = \frac{\frac{2}{27}}{1 - \frac{1}{3}} = \frac{\frac{2}{27}}{\frac{2}{3}} = \frac{2}{27} \cdot \frac{3}{2} = \frac{1}{9}.
        $$

#### Exercise 6
Let \(T\) be the time needed (in hours) to complete a job at a certain factory. By using the historical data, we know that:

\[
P(T \leq t) = 
\begin{cases} 
\frac{1}{16}t^2 & \text{for } 0 \leq t \leq 4, \\
1 & \text{for } t > 4.
\end{cases}
\]

1. Find the probability that the job is completed in less than one hour, i.e., find \(P(T \leq 1)\).

2. Find the probability that the job needs more than 2 hours.

3. Find the probability that \(1 \leq T \leq 3\).

??? answer

    1. Using the given formula for \(P(T \leq t)\) when \(0 \leq t \leq 4\):
   
        \[
        P(T \leq 1) = \frac{1}{16}(1)^2 = \frac{1}{16}.
        \]

    2. Using the complement rule:

        \[
        P(T > 2) = 1 - P(T \leq 2).
        \]

        Compute \(P(T \leq 2)\) using the given formula:

        \[
        P(T \leq 2) = \frac{1}{16}(2)^2 = \frac{4}{16} = \frac{1}{4}.
        \]

        Therefore:

        \[
        P(T > 2) = 1 - \frac{1}{4} = \frac{3}{4}.
        \]

    3. Using the subtraction rule:

        \[
        P(1 \leq T \leq 3) = P(T \leq 3) - P(T \leq 1).
        \]

        Compute \(P(T \leq 3)\):

        \[
        P(T \leq 3) = \frac{1}{16}(3)^2 = \frac{9}{16}.
        \]

        Compute \(P(T \leq 1)\) (already found in part (a)):

        \[
        P(T \leq 1) = \frac{1}{16}.
        \]

        Therefore:

        \[
        P(1 \leq T \leq 3) = \frac{9}{16} - \frac{1}{16} = \frac{8}{16} = \frac{1}{2}.
        \]

#### Exercise 7
You choose a point $(A,B)$ uniformly at random in the unit square $\{(x,y):0 \leq x,y \leq 1\}$.

<div style="text-align: center;">
    <img src="src/ex7.png" width="200">
</div>

What is the probability that the equation

$$
\begin{align*}
    AX^2+X+B=0
\end{align*}
$$

has real solutions?

??? answer
    \(\frac{1}{4}+\frac{1}{4} \ln 4 \approx 0.5966\)

    Also, see more elaborate solution [here](src/Solution7.pdf)


#### Exercise 8 (Exam 2014.2 (a+b))
An IT company receives its printed circuit boards from two different suppliers, 1 and 2. Records show that 5% of the circuit boards from supplier 1 and 3% of the circuit boards from supplier 2 are defective. 60% of the company’s current circuit boards come from supplier 2, and the remaining from supplier 1. The company usually keeps a stock of 2000 circuit boards. 

1. Based on this information, construct a contingency table of the company’s circuit board stock. Place supplier in the columns and defective/non-defective in the rows.
2. If a randomly chosen circuit board from the company’s stock is chosen and turns out to be defective, what is the probability that the circuit board is from supplier 1?

??? answer
    1. The contingency table is as follows:

        |               | Supplier 1 | Supplier 2 | Total |
        |---------------|------------|------------|-------|
        | **Defectives**    | 40         | 36         | 76    |
        | **Non-Defectives**| 760        | 1164       | 1924  |
        | **Total**         | 800        | 1200       | 2000  |

    2. The probability that a circuit board is from supplier 1 given that it is defective is:
   
        \[
        P(\text{Supplier 1} | \text{Defective}) = \frac{P(\text{Supplier 1} \cap \text{Defective})}{P(\text{Defective})} = \frac{40/2000}{76/2000} = \frac{40}{76} \approx 0.5263.
        \]

#### Exercise 9 (Exam 2015.2)
A batch of 1000 hard drives from three suppliers were tested. 2% of the hard drives from Toshiba and 2% of the hard drives from Seagate were defective, and in the entire batch there were 3% defectives in total. In the batch, 50% were Western Digital hard drives and 30% were Toshibas.

1. Based on this information, create a 3 x 2 contingency table of the hard drives.
2. What is the probability that a defective product came from Seagate?
3. What is the probability of randomly selecting a Western Digital hard drive from the entire batch?

??? answer
    1. The contingency table is as follows:

        | Supplier          | Defective | Non-Defective | Total |
        |--------------------|-----------|---------------|-------|
        | Toshiba (30%)      | 6         | 294           | 300   |
        | Seagate (20%)      | 4         | 196           | 200   |
        | Western Digital (50%) | 20        | 480           | 500   |
        | **Total**          | 30        | 970           | 1000  |

    2. The probability that a defective product came from Seagate is:
   
        \[
        P(\text{Seagate} | \text{Defective}) = \frac{P(\text{Seagate} \cap \text{Defective})}{P(\text{Defective})} = \frac{4/1000}{30/1000} = \frac{4}{30} = \frac{2}{15} \approx 0.1333.
        \]

    3. The probability of randomly selecting a Western Digital hard drive from the entire batch is:
   
        \[
        P(\text{Western Digital}) = \frac{500}{1000} = 0.5.
        \]

#### Exercise 10 (Exam 2016 New Test.3)
The probability that a regularly scheduled flight departs on time is 0.83; the probability that it arrives on time is 0.82; and the probability that it departs and arrives on time is 0.78. Find the probability that a plane

1. Arrives on time, given that it departed on time
2. Departed on time, given that it has arrived on time
3. Arrives on time, given that it did not depart on time

??? answer
    1. \(P(\text{Arrives on time} | \text{Departs on time}) = \frac{P(\text{Arrives on time} \cap \text{Departs on time})}{P(\text{Departs on time})} = \frac{0.78}{0.83} \approx 0.9398\)

    2. \(P(\text{Departs on time} | \text{Arrives on time}) = \frac{P(\text{Departs on time} \cap \text{Arrives on time})}{P(\text{Arrives on time})} = \frac{0.78}{0.82} \approx 0.9512\)

    3. \(P(\text{Arrives on time} | \text{Did not depart on time}) = \frac{P(\text{Arrives on time} \cap \text{Did not depart on time})}{P(\text{Did not depart on time})} = \frac{0.04}{0.17} \approx 0.2353\)