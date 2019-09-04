# Advanced algorithm

[课程网站](http://tcs.nju.edu.cn/wiki/index.php/%E9%AB%98%E7%BA%A7%E7%AE%97%E6%B3%95_(Fall_2019))，仅内网访问时可以加载讲义的数学公式。

**总的来说很有趣，也很有用，打算学下去。**

**推荐的参考书加入书单，有空大概会看吧。**

# Lec1

**Show case: what’s advanced algorithm?**

- 随机算法，min-cut问题。
- 近似算法，max-cut问题。

Recall: 

- 递归式看起来比较复杂的时候，时间多的话（比如做research）完全可以暴力猜测然后用induction证明。

Observation:

- 在随机算法中，因为选取参数不同时算法推进的代价不同，**分治与递归**的方法在这里有了新的应用！
- 卡住的时候换个角度思考问题，比如一开始考虑随机选取点到集合S或T中，成功概率很低，而通过思考cut的边的关系，从边入手很好地解决了问题。

---

**近似算法**

Greedy Heuristics并不见得是不好的。

最大化问题的近似比定义如下的第一项。注意首先选了一个最为理想的可能的$opt$，这是因为$opt$的表达式往往是没有closed form的，找到这个表达式可能本身就是一个NP-Hard问题：

App. ratio:$\frac{sol}{opt} \geq \frac{sol}{|E|}\geq \alpha$。

Observation:

- *合理建模能够加快分析过程*：把所有点看作排序的点序列后，其边至少为解的生成贡献了一半边，所以粗略地说近似比不小于二分之一。

