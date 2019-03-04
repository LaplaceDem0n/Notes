# GraphTheory_NJU

## Week1——Intro & Defs 图的基本概念

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

离心率：两个离得最远的点

中心

半径：

直径：

中位点：

A [metric space](https://www.wikiwand.com/en/Metric_space) defined over a set of points in terms of distances in a graph defined over the set is called a **graph metric**. The vertex set (of an undirected graph) and the distance function form a metric space, if and only if the graph is [connected](https://www.wikiwand.com/en/Connected_(graph_theory)).

The **eccentricity** ![\epsilon (GraphTheory_NJU.assets/829a4a4a595e508eea918455f8154ad189df595b-1551710032699.svg)](https://wikimedia.org/api/rest_v1/media/math/render/svg/829a4a4a595e508eea918455f8154ad189df595b) of a vertex ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) is the greatest distance between ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) and any other vertex; in symbols that is ![{\displaystyle \epsilon (GraphTheory_NJU.assets/d078af5df2ef5998f87f97e2b269ae3fc8c35825-1551710032708.svg)=\max _{u\in V}d(v,u)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d078af5df2ef5998f87f97e2b269ae3fc8c35825). It can be thought of as how far a node is from the node most distant from it in the graph.

The **radius** ![r](GraphTheory_NJU.assets/0d1ecb613aa2984f0576f70f86650b7c2a132538.svg) of a graph is the minimum eccentricity of any vertex or, in symbols, ![{\displaystyle r=\min _{v\in V}\epsilon (GraphTheory_NJU.assets/38af03e1b81b0a52bb946e56905bb831967000d4-1551710032715.svg)=\min _{v\in V}\max _{u\in V}d(v,u)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/38af03e1b81b0a52bb946e56905bb831967000d4).

The **diameter** ![d](GraphTheory_NJU.assets/e85ff03cbe0c7341af6b982e47e9f90d235c66ab-1551710032731.svg) of a graph is the maximum eccentricity of any vertex in the graph. That is, ![d](GraphTheory_NJU.assets/e85ff03cbe0c7341af6b982e47e9f90d235c66ab-1551710032731.svg) is the greatest distance between any pair of vertices or, alternatively, ![d=\max _{v\in V}\epsilon (GraphTheory_NJU.assets/f5c63eea6c9f40b4745dece06551878285877933-1551710032737.svg)](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5c63eea6c9f40b4745dece06551878285877933). To find the diameter of a graph, first find the [shortest path](https://www.wikiwand.com/en/Shortest_path_problem) between each pair of [vertices](https://www.wikiwand.com/en/Vertex_(graph_theory)). The greatest length of any of these paths is the diameter of the graph.

A **central vertex** in a graph of radius ![r](GraphTheory_NJU.assets/0d1ecb613aa2984f0576f70f86650b7c2a132538.svg) is one whose eccentricity is ![r](GraphTheory_NJU.assets/0d1ecb613aa2984f0576f70f86650b7c2a132538.svg)—that is, a vertex that achieves the radius or, equivalently, a vertex ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) such that ![\epsilon (GraphTheory_NJU.assets/f663f8ce21e01fdb49950e22c72e27e9d83d106c-1551710032745.svg)=r](https://wikimedia.org/api/rest_v1/media/math/render/svg/f663f8ce21e01fdb49950e22c72e27e9d83d106c).

A **peripheral vertex** in a graph of diameter ![d](GraphTheory_NJU.assets/e85ff03cbe0c7341af6b982e47e9f90d235c66ab-1551710032731.svg) is one that is distance ![d](GraphTheory_NJU.assets/e85ff03cbe0c7341af6b982e47e9f90d235c66ab-1551710032731.svg) from some other vertex—that is, a vertex that achieves the diameter. Formally, ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) is peripheral if ![\epsilon (GraphTheory_NJU.assets/78380210a073ddb9c281f418bf89215191e384a3-1551710032988.svg)=d](https://wikimedia.org/api/rest_v1/media/math/render/svg/78380210a073ddb9c281f418bf89215191e384a3).

A **pseudo-peripheral vertex** ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) has the property that for any vertex ![u](GraphTheory_NJU.assets/c3e6bb763d22c20916ed4f0bb6bd49d7470cffd8-1551710032988.svg), if ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) is as far away from ![u](GraphTheory_NJU.assets/c3e6bb763d22c20916ed4f0bb6bd49d7470cffd8-1551710032988.svg) as possible, then ![u](GraphTheory_NJU.assets/c3e6bb763d22c20916ed4f0bb6bd49d7470cffd8-1551710032988.svg) is as far away from ![v](GraphTheory_NJU.assets/e07b00e7fc0847fbd16391c778d65bc25c452597-1551710032702.svg) as possible. Formally, a vertex *u* is pseudo-peripheral, if for each vertex *v* with ![d(u,v)=\epsilon (u)](https://wikimedia.org/api/rest_v1/media/math/render/svg/226560062ddbd9f47ce86ea145c599fc501a910a) holds ![\epsilon (u)=\epsilon (v)](https://wikimedia.org/api/rest_v1/media/math/render/svg/9cb5cd1cef62d1583154466bdd03f94c872c6e93).

# Week one_hw

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