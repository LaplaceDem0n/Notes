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

-   往里代-替换法
    -   虽然一开始看着觉得很初级，但是实际上后面高级方法解不出来的用它反而很合适
-   特征方程
    -   记不住就完事了……
-   递归树->master定理
    -   $E=log_c b$
        -   每次均分为b个分支
        -   问题规模变成原来的$\frac{1}{c}$
    -   注意：$\varepsilon$必须**大于零**。如果无法找到大于零的$\varepsilon$，就不能使用两条规则。
        -   比如$T(n) = 2 T(n / 2) + n log n​$。

## Week 3-Quicksort

*排序算法实际上需要消除逆序对inversion pairs。*

*证明$\Theta\iff O\wedge\Omega$*.

## Review-Tutorial 1

### Useful $\sum$ Formulae

**TBD：** here.





# Q

特征方程实际上没什么用？



# 期中复习

## Points

1.  证明算法正确性
    1.  数学归纳法
    2.  （循环不变量）
2.  证明算法错误
    1.  举出反例（cotunerexample）
3.  平均时间复杂度计算
4.  时间复杂度记号与渐进增长率
5.  *Master定理与递归算法的复杂度计算
    1.  *Master定理不适用的情况(PS最后两题)
    2.  *Guess&Proof->substitution method(怎么Guess？)
        1.  n叉树的情况与lgn有关
        2.  $\sqrt n$的情况与lglgn有关
    3.  递归树分析（它是万能的吗？不是，但能够提供直观的推测，并便于用substitution method分析）
        1.   设$n=2^k$或$S(n)=T(2^n)$这样的换元技巧很好用
    4.  特征方程用得很少记不住？
6.  问题难度的下界与算法的最优性（排序问题中的逆序对与更通用的对手策略证明）

## 复习课要注意的PS中的题目

1.  Problem 2.2.4-广义逆序对
2.  Problem 2.3.1-D叉堆的计算
3.  Problem 2.3.2-思路？
4.  Problem 2.3.3-良好解法？

# 读书笔记

# 算法导论

## 为什么要研究算法

学会：

1. 自行设计算法
2. 证明正确性
3. 理解其效率



# 