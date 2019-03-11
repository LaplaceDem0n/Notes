# Algorithm_NJU

## Class info

In 00-prologue.pdf

**Examples**

-   Selection

    -   Find MAX & MIN simutaniouslly

-   Memory allocation

-   Predict horse 

    -   Huffman encoding & 信息熵 (Entropy)

-   Halting problem

    -   N
    -   NP
    -   NPC
    -   NP-Hard

    

    ### Textbook

    1/3 => PDF ver in QQ gruop.

    2 => 南大书不想买。

    

    ### Administrative things

    -   8次纸质作业
    -   6-8次OJ，每次Duration有2周左右。

## Week 1-Intro & Prelouge

### Proof

#### Double counting

-   Count the same thing twice-in this case, the triangle graph.

$$\sum\limits^n_{i=1}x^2=\frac{n(n-1)(2n+1)}{6}$$

#### 归纳Induction(Terminable & keeping the answers)

以欧几里得算法求gcd为例。

-   问题规模不断缩小，所以一定会终止
-   由数论知识知道所有的公约数都被保留



### Concept of Algorithm

### Criteria of Algorithm

-   Correctness & proof

-   Complexity

    -   Focus on critical operation
    -   Amount of work done
    -   Amount of space used
    -   Worst case complexity
    -   Average complexity
        -   Upper bound for algorithm
        -   Lower bound for problem

-   Simplicity, clarity

-   最优性Optimality

-   渐进分析Asymptotic
    -   Big O

    -   Other Sets

        $$\lim\limits_{n\to\infty}\frac{f(n)}{g(n)}=c\begin{cases}c=0, & f=\omicron(g) \\ 0\le c \lt\infty, & f=\Omicron(g)\\ 0\lt c \lt \infty, & f=\Theta(g)\\0\lt c\le \infty, & f=\Omega(g)\\ c=\infty, & f=\omega(g) \end{cases}$$

        Note:

        1.  右侧符号看做从小到大的蛋，中间一个有点东西，然后破壳，成长一点就扭曲了。
        2.  。
        3.  $\Omicron$传递性Transitive property
        4.  上下对称Symmetric properties
        5.  Order of sum function. $\Omicron(f+g)=\Omicron(max(f,g))$.

    -   $\lg n<n^\alpha<c^n<n!<n^n​$



### Divide and Conquer

### Decision tree

用有限的抽象来表述无限的算法。



## Week 2-Recursion

**How to compute recursion complexity function**

*注意：书写递归方程时，由于要保证输入为int，常添加*$\lfloor x\rfloor$。



三大方法：

-   往里代-替换法！
-   特征方程
-   递归树->master定理
    -   $E=log_cb$。
        -   每次均分为b个分支
        -   问题规模变成原来的$\frac{1}{c}$。



Q

特征方程实际上没什么用？