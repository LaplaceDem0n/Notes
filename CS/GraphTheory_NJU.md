# GraphTheory_NJU

## Week1——Intro & concepts 

阶order: $v(G)=|V(G)|$。读作纽。

size:$\epsilon(G)=|E(G)|​$。



多重集合：一组**可重复**的对象。



最大度$\Delta(G)$。

最小度$\delta(G)$。



零图 Null Graph => 没有点

空图 Empty Graph => （可以有点）没有边



$V'$点导出子图：$V'$选定，$E$取所有$v_i$间的$e$。记作$H=G[V']$。

$E'$边导出子图：$E'$选定，$V$取所有$e_i$连着的$v$。



同构： 记作$G\cong H$，判定两个图同构条件如下

-   $\exist V$之间的双射
-   点之间的相邻关系被保持（对应点间有边） 



walk->trail->path



极值证明法。

**自学部分**

离心率：一个点到图中另外一个点的最短路径的最长距离

中心：半径最小的点（这样的点不唯一）

半径：离心率最小的点的离心率

直径：离心率最大的点的离心率，图中两个点的最长最短路的距离

中位点：跳过



### 图的连通性

连通度$w(G)$。



## Week1_hw

### 同构

证明：非常复杂的问题。可以给出映射关系。

逻辑上可以这样做：

1.  在二部图中找到两个部分
2.  尝试根据部分的对应关系书写双射（单射+满射）
    1.  单射：一一对应
    2.  满射：所有元素都有对应

证伪：找到不同的同构不变量

1.  边数
2.  顶点数
3.  顶点度的升序
4.  是否k-正则
5.  是否二部图
6.  最长路径/环一样
7.  相邻关系相同
    1.  能找到一组互不相邻的顶点，其数目很大



## Week2-cut vertex,cut edge,connectivity

-   等价定义
    -   证明时的**工具**
    -   得知一个性质时同样可用的**新性质**

-   何时从逆否命题切入？
    -   任何->某个。能缩小讨论的范围，更容易讨论

### 证明的方式方法

-   不等式->反证法
    -   由图推式易，由式推图难
-   无限情况恒成立->数学归纳法
-   图论中的计算（2th PDF p23)
    -   穷举仅有的几个公式，如握手定理导出的$2\epsilon=\sum_{u\in V(G)}d(u)$



## Week2_hw

### 2.1

不会w

### 2.8

对K2（两个点的完全图）不成立。

但是图中点数大于等于三时容易证明成立。

### 2.22

？？？



## 名词解释



**Q:NPC和NPH问题不太正确，以后再改吧。**



### NP/NPC/P 问题

NP stands for "nondeterministic polynomial time".

NP代表“ 非确定性 多项式时间 ”。



**P问题**：存在多项式时间算法的问题。(P：polynominal，多项式)

**NP问题：**能在多项式时间内验证得出一个正确解的问题。(NP:Nondeterministic polynominal，非确定性多项式)。P类问题是NP问题的子集，因为存在多项式时间解法的问题，总能在多项式时间内验证他。

**NPC问题**:如果所有np问题都能在多项式时间内转化为他，则称该np问题为npc问题(NPC:NP complete又叫NP完全问题)。NPC问题是NP问题的子集。

**NPH问题**：我们又叫NP难问题，他不是一个NP问题，然后所有的NC问题都可以在多项式时间内转化为他的话，我们就叫他NPH（hard）问题。

>   NP-complete problems are in [NP](https://www.wikiwand.com/en/NP_(complexity)), the set of all [decision problems](https://www.wikiwand.com/en/Decision_problem) whose solutions can be verified in polynomial time; *NP* may be equivalently defined as the set of decision problems that can be solved in polynomial time on a [non-deterministic Turing machine](https://www.wikiwand.com/en/Non-deterministic_Turing_machine). A problem *p* in NP is NP-complete if every other problem in NP can be transformed (or reduced) into *p* in polynomial time.
>
>   NP完全问题在[NP中](https://www.wikiwand.com/en/NP_(complexity))，所有[决策问题](https://www.wikiwand.com/en/Decision_problem)的集合，其解可以在多项式时间内得到验证; *NP*可以等效地定义为可以在[非确定性图灵机](https://www.wikiwand.com/en/Non-deterministic_Turing_machine)上的多项式时间内求解的一组决策问题。如果NP中的每个其他问题都可以在多项式时间内转换（或减少）为*p*，则NP中的问题*p*是NP完全的。