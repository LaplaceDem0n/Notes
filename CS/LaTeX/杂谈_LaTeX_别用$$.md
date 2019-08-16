# LaTeX_别用$$



作者：知乎用户

链接：https://www.zhihu.com/question/27589739/answer/37237684

来源：知乎

著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

Update Log:

2015-01-14 23:13:47 感觉原始答案不够好，各位姑且看着，回头肯定得改。

TOC:

原始答案。

----- 原始答案 -----

在 LaTeX 数学环境里，有几个「要」和几个「不要」。其中之一就是「要用 \[ ... \]，而不要用 $$ ... $$」。

这其实是个老生常谈的问题了，不知道你搜索了什么，关键词「LaTeX Preferable dolars」是可以搜到不错的结果的。

以下是解释。

不推荐 $$ ... $$ 的原因大致有几个，根源都在于 $$ 很难在 LaTeX 里合适地重新定义。

国内的「间距有问题」大概最早来自 l2tabuen 这个文档的 1.6 节。（终端执行 texdoc l2tabuen，这个文档介绍了不少应该避免的命令、环境和宏包）文档是这么说的：

>   Please don’t do this! $$...$$ is a Plain TeX command. It will modify vertical spacing within formulae, rendering them inconsistent. This is why it should be avoided in LaTeX (see section 3.3 on page 15; note the warning concerning displaymath along with the amsmath.sty package). What’s more, class option fleqn won’t work any more. 
>
>   Replace: $$...$$ by \[...\] or
>
>   ```tex
>   \begin{displaymath}
>   ...
>   \end{displaymath}
>   ```

嗯，连带「不解释为什么」也是从这抄的。

为什么间距不对？

LaTeX2e 内核里的 \[ 是这么定义的：

```tex
  \ifvmode
     \nointerlineskip
     \makebox[.6\linewidth]{}%
  \fi
  $$
```

可以看到，实际上 \[ 和 $$ 还是脱不开关系的，只不过在 $$ 之前多加了一个判断。\ifvmode 是判断当前是否处于 vertical mode 的控制序列，大体可以理解为判断是不是处于两个段落之间。（具体的可以期待 

李阿玲

 的 primitives 系列专栏）

\nointerlineskip 的定义是 \prevdepth -\@m \p@。\@m 就是数字 1000，\p@ 是单位 pt。这么做可以去掉下一个行与行之间的 glue。这里 \makebox 的作用是让 $$ 开启的公式与 \makebox 形成的高度为 0 的行保持对齐。二者都是为了处理行间公式的垂直距离。而单独用 $$ 则没有这些处理，所以说它垂直间距不对。

在 amsmath 里，\[ 被重新定义为 \begin{equation*}。这里的处理就更复杂了，我就不详说了。

**还有没有别的？**

有，比如 l2tabuen 里提到的，fleqn 不对；还有在 proof 环境里处理 \qedhere 的时候也有问题。试编译如下代码，观察效果的差别。

```tex
\documentclass[fleqn]{article}
\usepackage{amsmath}
\usepackage{amsthm}

\begin{document}
\[
  E = mc^{2}
\]
$$
  E = mc^{2}
$$
\begin{proof}
  \[
    E = mc^{2}.\qedhere
  \]
\end{proof}
\begin{proof}
  $$
    E = mc^{2}.\qedhere
  $$
\end{proof}
\end{document}
```

![img](https://pic2.zhimg.com/50/f7ba6a90c9b9250dbb2bc2244fc193d4_b.jpg)![img](https://pic2.zhimg.com/80/f7ba6a90c9b9250dbb2bc2244fc193d4_hd.jpg)

可以看到，使用 \[ ... \] 的公式，按照 fleqn 的要求乖乖跑到左边去了，但是 $$ ... $$ 还倔强地立在中间；使用 \[ ... \] 的公式，能够正确地将证毕符号推到行尾，而 $$ ... $$ 则不行。

顺带一提。

其他还有一些数学环境里的「要」和「不要」。

-   用 $ ... $ 而不用 \( ... \)；
-   用 align 环境而不用 eqnarray 环境；
-   用 matrix, bmatrix, pmatrix, vmatrix, Vmatrix 等环境而不用 array 环境去实现矩阵；
-   用 \bigl, \bigr 等命令来处理定界符，而尽可能避免 \left 和 \right。

诸如此类，这些每一条，都可以写一个答案出来。（你们一定有人会去开题对吧……）

以上。