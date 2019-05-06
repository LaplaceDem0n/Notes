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
        3.  $\Omicron$传递性Transitive property
        4.  上下对称Symmetric properties
        5.  Order of sum function. $\Omicron(f+g)=\Omicron(max(f,g))$.
    
-   $\lg n<n^\alpha<c^n<n!<n^n$



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
        -   比如$T(n) = 2 T(n / 2) + n log n$。

## Week 3-Quicksort

*排序算法实际上需要消除逆序对inversion pairs。*

*证明$\Theta\iff O\wedge\Omega$*.

## Review-Tutorial 1

### Useful $\sum$ Formulae

**TBD：** here.

## Week9

### 图遍历

Why DFS/BFS? -> Intuitive

#### 图的表示

#### 从连通分量说起

1.  实现
2.  复杂度分析
3.  4 Edges

# Week11

## Review

White path theorem.



## New-Applications of DFS

1. Topological sort
2. Critical path
3. Strongly connected components

# Q

特征方程实际上没什么用？



# 期中复习

## Points

1.  证明算法正确性
    1.  数学归纳法
    2.  （循环不变量）
2.  证明算法错误
    1.  举出反例（cotunerexample）
3.  平均/最坏时间复杂度计算
4.  时间复杂度五记号与渐进增长率
5.  *Master定理与递归算法的复杂度计算
    1.  继续多练习~
    2.  *Master定理不适用的情况(PS最后两题)
    3.  *Guess&Proof->substitution method(怎么Guess？)
        1.  n叉树的情况与lgn有关
        2.  $\sqrt n$的情况与lglgn有关
    4.  递归树分析（它是万能的吗？不是，但能够提供直观的推测，并便于用substitution method分析）
        1.   设$n=2^k$或$S(n)=T(2^n)$这样的换元技巧很好用
    5.  特征方程用得很少记不住？
    6.  很多时候会用到数学上的技巧
        1.  逆因式分解
        2.  $\sum$的形式
            1.  配凑相减，将大部分重复项消去
            2.  积分放缩
6.  问题难度的下界与算法的最优性（排序问题中的逆序对与更通用的对手策略证明）
7.  Sort
    1.  复杂度和何种情况下坏
    2.  基于比较算法的Lower bound与决策树（review，逆序对只有2、3个的情况？——Google
    3.  EPL
8.  Select
    1.  加权中位数
    2.  对手策略
    3.  Hash

## 复习课要注意的PS中的题目

1.  Problem 2.2.4-广义逆序对
2.  Problem 2.3.1-D叉堆的计算
3.  Problem 2.3.2-思路？
4.  Problem 2.3.3-良好解法？

## 问题

1.  Quicksort平均情况复杂度的两种证明？

## 练习

1.  求解递归方程

2.  算法最优性的证明方法：

    1.  （排序）逆序对
    2.  信息量与对手策略
    3.  *决策树

3.  算法正确性的证明方法：

    1.  数学归纳三部曲：

        1.  归纳奠基
        2.  归纳假设
        3.  归纳递推

    2.  循环不变式三部曲：

        0.  选定要讨论的单个循环

        1.  初始化
        2.  维持（重点部分）
        3.  终止

    

## 不同复杂度能做的操作

1.  O(1+$\alpha$)
    1.  哈希
    2.  数组直接取
2.  O(lgn)
    1.  二分查找
    2.  FixHeap
3.  O(n)
    1.  乱序数组中取第k大/小个元素
    2.  遍历找最大
    3.  同时找最大最小
4.  O(nlgn)
    1.  对n个元素执行O(lgn)的操作
    2.  归并/快排
5.  O($n^2$)
    1.  大多数暴力算法





# 读书笔记

# 算法导论

##  第一章——算法在计算中的作用

**为什么要研究算法**

学会：

1. 自行设计算法
2. 证明正确性
3. 理解其效率

## 第二章——算法基础

### 插入排序

### 分析算法

记号、算法的平均/最差情况复杂度。

*注：从习题2.2-4中可知最好情况并不能说明算法本质*

### 设计算法（分治与递归）

Q：

1. 分治和动态规划的区别是什么？
2. P23，2-1d？？
3. 2-4c人话？

## 第三章——函数的增长

### 记号

多重函数与多重对数函数。Fib序列的近似增长速度。

*跳过练习*

## 第四章——分治策略







# 算法图解

## 图的遍历

Dijkstra不可处理负权值情况， Bellman-Ford可以。

## 近似算法之贪心算法

定义：贪心算法寻找局部最优解，企图以这种方式获得全局最优解

优点：对于NP完全问题，贪心能够较快地得到近似解。

判定NP完全问题：

1.  涉及“所有组合”的问题通常是NP完全问题
2.  不能将问题分成小问题，必须考虑各种可能的情况
3.  如果问题可以转化为几何覆盖问题或旅行商问题，它肯定是NP完全问题

## 动态规划

定义：将问题分成小问题，并先着手解决这些小问题。最后的解是小问题解的合并。

典型例子：

1.  背包问题
2.  最长公共子串

设计技巧：