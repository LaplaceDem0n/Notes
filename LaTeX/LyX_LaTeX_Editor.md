# LyX_LaTeX_Editor

[TOC]



# Chapter 1 介绍

## 1.1 欢迎来到 LyX!

这个文档是为那些不知道 LaTeX 或知之甚少的人准备的。不必担心，使用 LyX 不必学习 LaTeX。LyX 的目标就是提供一个所见即所得的 LaTeX 应用。为了高效的使用 LyX，还是需要学习一些东西的。

你会发现在其它字处理软件中常用的排版方式在 LyX 中都不能使用了，比如：在“.”后边输入两个空格，在段间输入三个空行。你以前使用的软件允许手动调整间距、字体等东西，所以你不得不即录入又排版。LyX会做好排版的事情的，而你只需要转注于重要的东西：你正在写的内容。

继续读下去，了解更多 LyX。读完这篇教程，你会觉得物有所值的。

## 1.2 本教程简介

在开始之前建议您先读一下 Introduction，那里解释了本文使用的注释方式。当你了解了各种字体的意义之后，我们先来说说本篇教程是干什么的。

### 1.2.1 学习方式

本教程包含了例子和练习。学习中您应该试着输入我们让你输入的东西，完成所有练习，看看您是不是得到了正确的东西。为了方便，将本文档打印出来会是一个好选择。

如果对 LaTeX 比较熟悉的话，你将能够较快的阅读本教程，因为 LyX 的思想就是 LaTeX 思想的一种包装。LyX 自身也有很多特性是你想了解的。就算不想继续读下去，你也应该看看 [5.2](file:///C:/Documents%20and%20Settings/Administrator/Local%20Settings/Temp/lyx_tmpdir.Hp3984/lyx_tmpbuf7/Tutorial.xhtml#sec_LaTeX_____________)，它是专门写给熟练的 LaTeX 用户的。

### 1.2.2 本教程没有的

-   LyX 全部特性的详细解释。

    需要的话，请阅读 the *User's Guide。*

    

-   LaTeX 的详细解释。

    没必要这样做。要想知道用 LaTeX 在 LyX 中能做些什么，可以看看 the *Embedded Objects* manual。

    

现在是开始你的第一个文档的时候了。

# Chapter 2 初识 LyX

## 2.1 第一个 LyX 文档

开始之前说几件事情，这会使本教程发挥更大的作用。

由于本教程不会提供所有信息，所以你需要找到其它的帮助文件。这很简单：启动 LyX，在帮助菜单中就有 the *User's Guide。在写自己的文件时就可以读到它们了（它们本身就是很好的例子）。注意，当打开多个文件时，可以通过 View 菜单或文档标签进行切换。*

我们假设你已经有了全功能的 LyX 和 LaTeX，包括 DVI、PDF 文件浏览器。一般来说，在各种操作系统上，在安装 LyX 的时候就已经做好了。

最后，我们提供了一个文件 example_raw.lyx，给你练习使用。假想这个文件是由一个完全不知道 LyX 特性的人写的，在学习的过程中，我们会建议你修改这个文件的。example_raw.lyx 中也包含了修改的提示信息。为了对比，我们还提供了一份 LyX 高手写的同样内容的文档：example_lyxified.lyx。

示例文档存在于 LyX 安装路径的 examples 目录下。打开示例文档，另存到自己的目录下，修改后输出到 DVI 文件看效果。

另外，examples 目录中还有很多其它的示例文件，它们将向您展示 LyX 的强大功能。当你忘记了某个功能怎么使用的时候，也可以回来看看这些文档。

### 2.1.1 录入、查看、输出

-   使用菜单 File⇒New 打开新文件。

-   输入一个句子: This is my first LyX document!

-   使用菜单 File⇒Save As 保存文件。

-   运行 LaTeX 生成 DVI 文件，使用菜单 View⇒DVI 或 工具栏按钮 ![image:2F__Program_Files_LyX20_bin____Resources_images_buffer-view_dvi.png](http://blog.sciencenet.cn/static/js/grey.gif) 。 LyX 将打开 DVI-viewer 程序显示文档打印时的样子。

    **1**

    

-   使用菜单 File⇒Export 将文档输出成希望的格式。

恭喜！你已经写出了第一个 LyX 文档。其余的细节，你会在其它手册中读到。

### 2.1.2 简单操作

LyX 能够做到其它软件能做的绝大部分事情，如：自动换行、段落缩进……以下是几个简单操作的使用方法。

-   撤消

    LyX 有多级撤消功能，你可以使用 Edit⇒Undo （或工具拦按钮 ![image:4F__Program_Files_LyX20_bin____Resources_images_undo.png](http://blog.sciencenet.cn/static/js/grey.gif) ）来撤消本次编辑会话开始以来的所有操作。如果撤消过头了，可以选择 Edit⇒Redo （或工具栏按钮![image:5F__Program_Files_LyX20_bin____Resources_images_redo.png](http://blog.sciencenet.cn/static/js/grey.gif) ）恢复。目前撤消操作支持100步，而且撤消也不是能够支持所有更改的，比如对文档布局的更改就不能被撤消，这的确是一个 bug。

-   剪切/粘贴/复制

    使用 Edit⇒Cut （工具栏按钮 ![image:6F__Program_Files_LyX20_bin____Resources_images_cut.png](http://blog.sciencenet.cn/static/js/grey.gif) ）， Edit⇒Copy （工具栏按钮 ![image:7F__Program_Files_LyX20_bin____Resources_images_copy.png](http://blog.sciencenet.cn/static/js/grey.gif) ），和 Edit⇒Paste （工具栏按钮 ![image:8F__Program_Files_LyX20_bin____Resources_images_paste.png](http://blog.sciencenet.cn/static/js/grey.gif) ） 来实现剪切、复制和粘贴操作。或者也可通过鼠标中键来粘贴选中的文本（包括其它程序中选定的文本）。

-   查找/替换

    点击 Edit⇒Find & Replace （工具栏按钮 ![image:9F__Program_Files_LyX20_bin____Resources_images_dialog-show_findreplace.png](http://blog.sciencenet.cn/static/js/grey.gif) ） ，在出现的对话框中点击按钮“Find Next” 进行搜索，点击按钮“ Replace”替换搜到的字词。 **2**  你还可以指定区分大小写或全字匹配，当然也可以反向搜索文档。

-   字符格式

    用 Edit⇒Text Style 对话框中的 toggle buttons ，可以强调（默认斜体）、加粗或设置为无格式（字体一般较小，用于人名）。

-   工具栏

    菜单支边的工具栏提供了一些常用功能的按钮，例如：粘贴、打印。

当然，目前还没有输入足够多的内容以使所有这些功能可用。

### 2.1.3 所见即所想：LyX 中的空白

对新用户来说，最难理解的是 LyX 处理空白的方式。敲多次回车只能得到一个空行；敲多次空格只能得到一个空格。在空白行上，连一个空格都无法得到。按下 Tab 键也不会移动一个 Tab 位；实际上就没有 Tab 位！在页面上方也没有标尺可供设置 Tab 位和边距。

很多字处理软件建立在 WYSIWYG 理念之上，也就是：看到的就是得到的（所见即所得）。LyX 不同，它建立在 WYSIWYM （所想即所得）的理念之上。你想什么就输入什么，LyX 会处理排版的问题，这样保证了输出文件的美观。回车分段，空格断词，没理由在一行中输入好几次空格。Tab 根本就没有语法意义，所以 LyX 不支持它。使用 LyX，你将花费更多的时间去考虑文档的**内容**，而不是它的**格式**。更多关于 WYSIWYM 的解释参见 *Introduction。*



LyX 的确也有不少精细调整文档格式的方法。毕竟 LyX 可能不会 100% 精确的按照你想的去排版。

User's Guide 包含了调整文档格式的详细方法，包括水平填充（HFills）和垂直距离（它们比空格、回车更加强大灵活）；设置字体大小 、样式的方法；调整段落对齐方式的手段。你只需要专心写你的文档，在最后细调一下文档格式就好了。使用普通的字处理软件，你会在写文档的整个过程中都被格式排版所困扰。

 

*3*

## 2.2 环境

文档的不同部分有不同的作用，我们称这些部分为“环境”（*environments*）。标题告诉读者新的话题（子话题）将会开始。某些文档含有特殊的环境，比如：期刊会有摘要和题目；书信就没有摘要和题目，但它有地址。

环境是 LyX 所见即所得哲学的重要部分。一个环境需要具体的定义：字体大小、样式、缩进、行间距等等。这个问题非常重要，因为一个给定环境的具体定义会随着文档类型的变化而变化。比如：某期刊要求标题是黑体、18pt、居中，而另一个可能要求斜体、15pt、左对齐；不同的语言也有不同的缩进标准；参考文献的格式就变化更大了。LyX 会把你从这些格式中间拯救出来。

你可以使用工具栏上的环境下拉菜单![image:10F__Program_Files_LyX20_bin____Resources_doc_clipart_ToolbarEnvBox.png](http://blog.sciencenet.cn/static/js/grey.gif) 来选择环境，它也能告诉你当前的环境是什么，其中“Standard”是文本的默认环境。现在我们将在你的新文档中添加几个环境，来看看它们是怎么工作的吧。

### 2.2.1 节（Section）与子节（Subsection）



在 LyX 文档的第一行输入“Introduction”，在环境下拉菜单中设为“节”（Section）

 

**4**

 

， 确定你选择了“节”（Section）而不是“节*”（Section*）。LyX 将在前边加上“1”并把字体调大。现在敲回车，环境将从“节”（Section）变回“标准”（Standard）。和多数环境类似，敲回车后环境将终止。输入文本：

This is an introduction to my first LyX document.

再次回车，选择“节”（Section）环境，LyX 将写上“2”并等待输入。现在输入“More Stuff”，LyX 会把它设置成节（Section）标题的样式。

将光标定位到节 1 （Section 1）末尾，敲回车，再次设置为“节”（Section），LyX 会写上“2”并等待输入。输入“About This Document”。刚才的节 2 （Section 2），“More Stuff”，现在已经被改成了节 3 （Section 3）。你只需要确定哪些文字是节（Section）标题，LyX 会处理编号和排版格式的，这就是所见即所想（WYSIWYM）的风格。

敲回车，回到“标准”（Standard）环境，输入下边 5 行文字：

Sections and subsections are described below.

Section Description

Sections are bigger than subsections.

Subsection description

Subsections are smaller than sections.

点击第二行，在环境下拉菜单中设为“子节”（Subsection）。LyX 将会在前边加上“2.1”，并把字体调整的比正文大，比节（Section）标题小。接着把第 4 行也设置成为“子节”（Subsection），LyX 将在它前边加上“2.2”。如果在节 2 （Section 2）前边加上了别的节，节 2 将会自动变为节 3（Section 3），后边的子节也会跟着变成“3.1”和“3.2”。

文档的层级结构还有次子节 ( Subsubsection )、段 ( Paragraph ) 和子段 ( Subparagraph )，这些就由读者自行把玩吧。段和子段的标题默认是不编号的，而且子段还有缩进，参阅 *User's Guide* 得到更多解释以及如何改变它们。章（Chapter）是文档层级结构中最高的一级，只能在某些特定的 LyX 文档类型中才能使用它（见 [3.1](file:///C:/Documents%20and%20Settings/Administrator/Local%20Settings/Temp/lyx_tmpdir.Hp3984/lyx_tmpbuf7/Tutorial.xhtml#sec__________)）。

你可能还希望一些节和子节是不编号的，LyX 有专门的环境实现这个功能。当把节的标题环境改为“节*”（Section*）后，LyX 还将对它使用相同的字体，只是不再对它进行编号。相应的也有带“星”的子节和次子节环境。试着把一些节或子节的标题环境改为带星的，同时看看其它的编号怎么随之改变。

练习：修改 example_raw.lyx 中的节和子节标题。

### 2.2.2 列表（Lists）和子列表（sublists）

LyX 有好几种列表环境，在写提纲或者重新排序一个已有的列表时，这些列表环境会帮上大忙。不同的文档类型需要不同的列表环境：

-   幻灯片使用带圆点的条目环境（Itemize）。
-   大纲使用带编号的枚举环境（Enumerate）。
-   名词解释常用描述环境（Description）。
-   列表环境（List）和描述环境（Description）差不多，只是对齐方式稍有不同。

现在我们写一个 LyX 有关优点的列表。在文档中输入：

LyX is better than other word processors because:

然后敲回车，并在环境下拉列表中选择条目环境（Itemize）。LyX 会在行首加上圆点。继续输入：

Typesetting is done for you.

Math is WYSIWYG

Lists are very easy to create!

和标题不同，列表环境在敲回车时不会终止，LyX 会认为你将继续写下一个条目。所以上边的输入将会产生三个列表项。重新选择标准环境（Standard）或使用快捷键 Alt+P S 才能退出列表环境。要在一个列表项中使用多个段落，可使用保护性中断（Protected Break），按下 Ctrl + 回车即可。



你已经得到了一个漂亮的条目列表，你是不是已经迫不及待的想运行 LaTeX 看看它们打印出来的样子了？可如果您想给它们加上编号呢？你只需要选定整个列表

 

**5**

 

，然后选择枚举环境（Enumerate）即可。如果你增删条目的话，LyX 会自动修改枚举编号的。



现在列表项还是处于被选定状态的，你可以再试试描述（Description）和列表（List）两种环境。这两种环境都是名词加定义的形式，描述环境前边的名词用黑体，列表环境的名词和后边的定义由“Tab”

 

**6**

 

分隔。前边的名词如果多于一个词的话，需要使用保护性空格（Protected

 

Blanks）将它们分开。

练习：排版 example_raw.lyx 中的列表。

这些列表环境还可以嵌套使用，提纲就是最常见的例子。带编号或圆点的列表在子列表中会有不同的表现形式。更多详情参见 *User's Guide* 。

### 2.2.3 其它环境：诗、引用和更多

有两种引用环境：短一点的引用使用引用环境（Quote）；长一点的引用使用引文环境（Quotation）。计算机代码使用代码环境（LyX-Code），该环境使用typewriter 字体，而且这里是 LyX 中唯一允许使用多个空格的地方。你还可以使用诗环境（Verse）来写诗：回车分节，Ctrl + 回车断行。对所有环境的完整描述参见 *User's Guide*。

练习：修改 example_raw.lyx 中的引用、代码、诗环境。

# Chapter 3 编辑文档

前边的章节讲解了 LyX 的基本操作和环境的使用方法，使大家对 LyX 有了一个初步的了解。而大部分人使用 LyX 是为了写文档的，比如：论文、书、手册或书信。本章将学习编辑完整的文档，你将学到文档类、标题、脚注、交叉引用、参考文献和目录的使用方法。

## 3.1 文档类



不同的文档有不同的排版方式，例如书籍是双面打印，文章是单面打印。文档还可能有特殊的环境，书信有发信人地址和签名两个环境，这两种环境在书籍和文章中就不起作用。LyX 的文档类

 

**1**

 

会处理不同文档种类中不同的排版方式。本教程使用的就是书籍文档类。文档类是所见即所想哲学的一个重要部分，它告诉 LyX 怎样排版，所以你不需要知道太多。



你的文档可能是用文章（Article）文档类

 

**2**

 

的，换到其它的文档类（使用 Document⇒Settings 对话框）看看有什么不同。切换到书籍类时，你会发现在环境下拉框中大部分的选项差异不大，只是现在可以使用“章”环境（Chapter）了。如果不能确定应该使用哪种文档类，你可以看看环境下拉框里边的东西。



各种杂志期刊排版区别主要在于字体大小、单双栏、页眉等地方。随着计算机时代的到来，期刊开始接受电子投稿，只要建立相应的 LaTeX 样式文件（style files），作者们就可以提交正确排版的文章了。LyX 就可以通过 Article

 

(AMS) 文档类支持美国数学学会会刊。

 

**3**

这是几个文档类的简单描述，更多信息参见 *Additional Features*。



| Name                   | Notes                    |
| ---------------------- | ------------------------ |
| 文章（article）        | 单面、无章               |
| 文章 （article AMS）   | 美国数学学会专用         |
| 报告（report）         | 比文章长、双面           |
| 书籍（book）           | 报告加上前后的一些零碎儿 |
| 幻灯片（presentation） | 透明                     |
| 书信（letter）         | 包含地址、签名等特殊环境 |

## 3.2 模板：写一封信

要写信，你只需要新建一个文件并从 Document⇒Settings 对话框中设定书信文档类就行了。但每次写信都需要设定发信人地址、收信人地址、正文、签名等环境，LyX 的书信模板可以省下不少时间，你只要替换模板中相应部分的文字即可。

点击菜单 File⇒New from Template，并选择 letter.lyx 模板。保存打印，看看不同的环境是怎么排版的。

在环境下拉列表框中，你会看到几个书信文档类独有的环境，如：我的地址环境（My Address）。建议在这儿把这些环境一个一个的都试试。你可能会注意到签名环境（Signature），签名文字前边有个红色的“Signature：”标签，该标签并不出现在打印出来的书信中。它就是告诉你这里有你设置的签名，它出现在哪里也不重要，LyX 是所见即所想的，无论把它放在哪里，LyX 都知道在打印时它应该出现在最后。



模板本身是一个 LyX 常规文件，你可以修改一下另存为一个新的模板。下次写信时，使用新模板会节省时间。这里我们没有建议的练习，你就给某人写封信吧。

 

**4**

鉴于使用模板能够节省大量时间，我们强烈建议您使用它。另外它们还能够帮助人们学习其它新奇的文档类。如果您想把 LyX 介绍给不太会用计算机的人使用的话，模板也能帮上忙。模板还能降低初学者对 LyX 的恐惧感。

## 3.3 文档标题

标题包括题目、作者、日期、摘要。LyX 把标题视为文档中单独的一部分。



新建一个 LyX 文档，令其使用文章文档类（Article）。

 

**5**

 

在第一行写上题目并令其为标题环境（Title），下一行写上你的名字并设为作者环境（Author），再下一行写上日期并设为日期环境（Date）。然后再写上一两段摘要，并设为摘要环境（Abstract）。看看这些东西打印出来后是什么样子的。如果把文档设为书籍类，将会得到一个单独的标题页，看起来就像本教程的第一页。

练习：在 example_raw.lyx 中修改标题、日期、作者。

## 3.4 标签（Labels）与交叉引用（Cross-References）

你可以为章节标题、列表项、公式、脚注、浮动体（floats）添加标签，之后可在文档的其它部分通过交叉引用引用它们，可以引用章节编号也可以引用页码，LyX 当然也会自动计算交叉引用的编号。自动标签和交叉引用是 LyX 相对于其它字处理软件的显著优点。

### 3.4.1 标签

我们回到第一个文档的第二节，它的标题是“About This Document”。将光标定位至该行末尾，选择 Insert⇒Label 或工具栏按钮 ![image:11F__Program_Files_LyX20_bin____Resources_images_label-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) 。在对话框中输入标签名，点击 OK 后，标签名将会出现在行尾。

节标签可以放在节的任意位置，节的引用将会指向离标签最近的一个节或子节。你可以把节标签放在节标题上，或者是节的第一行上边，这样可以保证引用的页码会是节的开始页。

到目前为止，我们还没做什么事情，输出的 DVI 文件也不会有什么变化，因为标签是不会出现在打印文档中的。现在已经添加了一个标签，下边我们将会通过交叉引用来引用它。

### 3.4.2 交叉引用

将光标定位到文档的节 2，输入

If you want to know more about this document, then see 
section, which can be found on page.

然后将光标放在单词“section”后边，选择 Insert⇒Cross Reference 或点击工具栏按钮 ![image:12F__Program_Files_LyX20_bin____Resources_images_dialog-show-new-inset_ref.png](http://blog.sciencenet.cn/static/js/grey.gif) 调出交叉引用对话框。你将会看到可用的标签列表，当然现在只有一个：“sec:About-This-Document”，选定它并点击应用（Apply）按钮。现在再把光标定位到单词“page”后边，并把引用格式改为页码，最后再点击应用。（为了保证排版的正确性，应该在单词“section”和引用之间放置一个保护性空格（Protected Blank）。对页码的引用也是这样。）

另外还可以在标签上右击，在上下文菜单（右键菜单）中选择“复制为引用”（Copy as Reference）。这样当前标签的交叉引用就已经复制到了剪贴板中，在需要的地方粘贴即可。

LyX 会将交叉引用放在光标所在位置。在打印出来的文档中，引用将会被替换成页码或节编号（这要看引用格式是怎么设置的了）。在输出的 DVI 文件中，我们会看到对节 2（Section 2）和页 1（Page 1）的引用。

点击交叉引用将会出现交叉引用对话框，点击转至标签（Go to Label），光标将会定位到引用标签。这个功能还真有点像超链接。

### 3.4.3 关于标签的更多讨论

前边说过，LyX 会自动计算交叉引用的编号，现在来试试这个功能。在节 2 前边添加一个新节，更新 DVI 输出文件，对节的交叉引用已经变成 3 了。再把“About this Document”设置成子节（subsection），引用将会从 3 变为 2.1 。当然，不在标签前边添加一整页文字的话，引用的页码是不会改变的。

你可以再多添加几个标签，在其它地方引用一下。如果使用交叉引用比较多的话，开着交叉引用对话框是个好主意。



还可以从 User's Guide

 

那里，复制些文字过来

 

*6*

 

，检验一下对页码的引用是不是正确。

练习：修正 example_raw.lyx 中的引用。

## 3.5 脚注（Footnotes）与旁注（Margin Notes）

点击工具栏按钮 ![image:13F__Program_Files_LyX20_bin____Resources_images_footnote-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) 或菜单 Insert⇒Footnote，将会在当前位置插入脚注。在文档中找到单词“LyX”，将光标定位在它后边，点击工具栏按钮 ![image:13F__Program_Files_LyX20_bin____Resources_images_footnote-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) ，脚注框将会出现在“LyX”后边，可以在里边输入脚注文字，现在输入

LyX is a typesetting word processor.

脚注文字前边有一个灰框，写着“脚注 x”（foot x），这里的“x”是脚注编号，点击它，脚注框将会关闭，光剩下那个灰框，这个动作称为“折叠”（folding），再次点击又会“展开”（unfold）。以后可以随时展开它重新编辑脚注文字。

这一段已经过时，跳过不译。

脚注也可以像普通文字那样剪切、粘贴，选定脚注的灰框后就可以粘贴了。另外，选定一段文本再点击按钮 ![image:13F__Program_Files_LyX20_bin____Resources_images_footnote-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) ，你就可以将一段文本转换为脚注了。要将从脚注变为常规文字，只需要将光标定位在脚注文字的最前边后再按下退格键（Backspace），或者将光标定位在脚注文字的最后边再按下删除键（Delete）。

使用菜单 Insert⇒Marginal Note 或工具栏按钮 ![image:14F__Program_Files_LyX20_bin____Resources_images_marginalnote-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) ，可以添加旁注。旁注和脚注从功能上说是类似的，其不同之处在于：

-   屏幕上旁注显示为“旁注”（margin），脚注显示为“脚注”（foot）。
-   旁注文字显示在页面旁边，脚注文字显示在页面底部。
-   旁注不编号。

将脚注转变为常规文字，再把它们转变为旁注。运行 LaTeX 看看旁注是什么样的。

练习：修正 example_raw.lyx 中的脚注。

## 3.6 参考文献（Bibliography）

参考文献和交叉引用有点像，它在文档末尾有一个引用列表，你可以在文档中引用它们。和章节标题一样，LyX 和 LaTeX也会为您自动计算参考文献的编号，当编号改变时，引用也会随之改变。

定位至文档末尾并切换至参考文献环境（Bibliography），你输入的每一个段落都将成为一个被引用对象。现在输入第一个引用项：“The Lyx Tutorial, by the LyX Documentation Team”。LyX 将会在每个引用项前边的框加上编号，点击引用项前边的框参考文献项（Bibliography item）对话框就会出现。其中“键”（key）是 LyX 中标识该引用项用的，标签（Label）将会出现在输出文档中。标签项没有被设定时（默认如此），输出文档中就会出现参考文献的编号。为了方便记忆，把“键”（key）设定为“lyxtutorial”。



现在将光标定位至文档中要引用该文献的地方，选择 Insert⇒Citation 或工具栏按钮

 



 

，将出现引用对话框（Citation dialog）。对话框中左侧

 

**7**

 

面板列出了可用的文献项，选择“lyxtutorial”并点击添加按钮（Add）指定将引用的文献（可指定多个），最后点击确定或应用按钮插入文献引用（原文中少了这一步操作）。查看输出文件，你会看到方括号中以编号或标签的形式引用了文档末尾的参考文献项。

引用对话框中的注释字段会在方括号中引用文献后边添加一个注释，用以说明引用的是哪一页或哪一章。要想引用文献的标签而不是编号的话，在参考文献项对话框（Bibliography item dialog）中设定标签值即可。更多信息参见 *User's Guide*。

练习：修正 example_raw.lyx 中的参考文献项和引用。

## 3.7 目录（Table of Contents）

用 LyX 在文档开始添加目录非常简单：在文档标题后敲回车，选择 Insert⇒List / TOC⇒Table of Contents 就可插入目录了。这时文字“Table of Contents”以按钮的形式出现在文档的第一行。

输出文档后，你会发现目录已经生成了，它列出了文档中的章节标题。修改文档的章节后，重新输出文档，目录也会随之改变。



为了保证文档的可读性，LyX 的编辑窗口中并不显示目录内容。选择 Document⇒Outline 或工具栏按钮

 



 

，将在一个新开的提纲窗口（Outline window）中显示目录内容。就算你没在文档中插入目录，这一操作依然有效。当你需要在文档各部分间快速切换时，这一工具会变得相当有用。在提纲窗口中点击某一章节标题将会高亮显示该行，并在编辑窗口中定位至该章节。你也可以使用方向键在目录中移动

 

**8**

 

。编辑文档时开着提纲窗口将会很方便。导航菜单（Navigate）也能提供类似功能。

删掉 Table of Contents 按钮就能删掉目录了。

练习：修正 example_raw.lyx 中的目录。

# Chapter 4 数学公式

不少科学家使用 LaTeX，这是因为它能够输出漂亮的公式，还不用使用其它字处理软件的控制字和它们的公式编辑器。但这些科学家中有不少人觉得 LaTeX 很难用，因为它用起来不像是在写文章，而像是在编程。LyX 能够很好的解决这个问题，它对公式能够实现所见即所想。如果熟悉 LaTeX 的话，你会发现以前常用的 LaTeX 的数学命令都能被 LyX 正确识别，而且能够显示成最后输出时的样子。如果不会使用 LaTeX的话，你照样能通过数学面板简单快速的输入漂亮的数学公式。

## 4.1 数学模式

在你的文档中输入：

I like what Einstein said, E=mc^2, because it's so simple.

现在你的公式并不能被正确显示，因为 LyX 并不知道你是在输入公式，所以它按照常规文本来处理输入的公式。

要输入公式，只要点击工具栏上的按钮 ![image:17F__Program_Files_LyX20_bin____Resources_images_math-mode.png](http://blog.sciencenet.cn/static/js/grey.gif) 或使用菜单 Insert⇒Math⇒Inline Formula，LyX 就会插入一个蓝色方框，这就是一个空的公式。现在再输入 E=mc^2 就行了。在公式中输入字符后，蓝色方框会消失。按下 Esc 退出公式输入状态，公式四角的紫色标记会消失并将光标定位在公式右边。再输入文字时，LyX 会按照常规字符来处理它们的。

将文档输出后，你会看到公式已经被正确排版了。等号两边都留有间距，数字“2”也被放到了上标的位置。在数学模式下数字就被看作数字处理，英文字符被视为变量并使用斜体排版。



LyX 的公式编辑器是所见即所得哲学的又一个例子。LaTeX 中用文本和命令输入公式，如：\sqrt{2}，将文档输出后才能看到公式的真正样子，在编辑状态下，一般人是很难发现所输入公式的错误的。虽然 LyX 并没有试着让公式在编辑状态下就显示的非常完美，但它的确让人看到了所输入公式的样子。输出时 LaTeX 再接手对公式进行专业的排版。

 

**1**

## 4.2 在公式中导航

现在把 E=m c 2 改为 E=1+m c 2 。使用方向键将光标移入公式中，公式四角会出现紫色标记告诉你现在正在编辑公式。按下方向键将光标定位在等号后边，输入“1+”。使用方向键将光标移出公式或使用 Esc 退出公式编辑状态。

在公式中的编辑操作和常规文字的编辑没有区别，不再详述。

如果想把 E=m c 2 改为 E=m c 2.5 +1 ，你需要将光标定位至公式相应的位置上修改即可。要注意的是上下标的编辑方式，如果使用鼠标进行定位的话，公式正文和上下标的位置是不容易区分的。你可用方向键将光标定位到字母“c”后边、数字“2”前边，按下方向键“上”后你就可以修改上标了。完成后再按方向键“下”或空格回到公式正文编辑状态。

## 4.3 指数与上下标

输入指数时，你可以使用界面下方的工具栏或直接输入“^”，LyX 会在上标位置放置一个蓝色方框，接下来输入的字符会被视为上标。上标输入完成后按空格回到公式正文编辑状态。类似指数的输入，输入下标只需键入“_”。

练习：将 example_raw.lyx 中的公式 1 改为数学模式。

## 4.4 数学工具栏

使用数学工具栏可以输入各种符号和复杂的公式。虽然使用键盘和菜单也能实现这些功能，但现在我们只讨论如何使用数学工具栏。以后你可以从其它手册中学到如何使用快捷键输入。

进入公式编辑状态后，数学工具栏会自动出现在界面下方。你也可以使用菜单 View⇒Toolbars⇒Math 将其永久调出。

### 4.4.1 希腊字母与符号

使用数学工具栏你可以输入很多数学符号，包括：各种箭头、关系、运算符、求和求积符号。求和、求积的上下限可以使用上下标实现。

在这里你无所不能。

### 4.4.2 根号、重音与定界符

点击按钮 ![image:18F__Program_Files_LyX20_bin____Resources_images_math_sqrt.png](http://blog.sciencenet.cn/static/js/grey.gif) ，LyX 会插入根号并将光标定位在根号下的蓝色方框中。你可以在里边输入任何公式符号，LyX 会自动缩放根号大小以适应输入的公式。

可以使用重音修饰单个字符（ v ⟶ ）或一组字符（ a+b ⟶ ），方法都是相同的。点击按钮 ![image:19F__Program_Files_LyX20_bin____Resources_images_math_hat.png](http://blog.sciencenet.cn/static/js/grey.gif) ，LyX 将插入该修饰并附带一个输入点，在这里输入字符即可。有两种修饰类型：一个是自动缩放的；另一个是固定尺寸的。固定尺寸的适合修饰单个字符。

定界符（小括号、中括号、大括号）的用法都差不多，点击按钮 ![image:20F__Program_Files_LyX20_bin____Resources_images_dialog-show_mathdelimiter.png](http://blog.sciencenet.cn/static/js/grey.gif) 出现一个对话框，在里边选择你需要的即可。默认时，两边的定界符是匹配的，取消“keep matched”复选框后也可以把两边的定界符设置成不同的。例如： a=⁡langle7. ，“7”的右边就没有使用定界符。

觉得麻烦的话也可以直接用键盘输入括号，不过这样输入的括号和常规文本一样都是固定大小的。如果括号中有大个的分式或矩阵的话，公式就会很难看，看了下边的公式你就明白了。 ( 1 2 2 1 3 + 2 )=⁡( 1 2 2 1 3 + 2 )

选定公式的一部分后再从面板插入根号、重音或定界符，看看发生了什么？

练习：把 f=ma 变为 f ⟶ =m a ⟶ 。

### 4.4.3 分式



使用数学工具栏按钮

 



 

插入分式，LyX 将在分式上创建两个输入点，并将焦点定位在上边的输入点上，你可以使用方向键或鼠标在这两个输入点间切换

 

**2**

 

。在这两个输入点上输入公式，就能得到所需的分式了。

练习：修正 example_raw.lyx 中的公式 2。

### 4.4.4 TeX 模式：lim、log、sin与其它

由于公式中的字符都被视为变量，所以输入的“sin”会被看作是三个变量 s 、 i 、 n 的乘积，并使用 Roman 斜体显示，而且在 sin 和 变量 x 之间也没有额外的间距。应该如何得到 sin⁡(x) 而不是 sin⁡(x) 呢？

点击数学工具栏上的按钮 ![image:22F__Program_Files_LyX20_bin____Resources_images_math_functions.png](http://blog.sciencenet.cn/static/js/grey.gif) 并选择“sin”，LyX 将输入“sin”并将其设为黑色 Roman 正体。“sin”这三个字符被视为一个整体，删除也是一起删除。然后再输入“(x)”，它们将被显示为蓝色斜体。在输出文件中，公式将会被正确排版。

在按钮 ![image:22F__Program_Files_LyX20_bin____Resources_images_math_functions.png](http://blog.sciencenet.cn/static/js/grey.gif) 的函数列表中还有其它三角函数及其反函数、双曲函数、对数、极限等。这些函数都可以接受上下标，如：“ cos 2 θ ” 和 “ lim n → ∞ ”。

练习：修正 example_raw.lyx 中的公式 3。

### 4.4.5 矩阵

点击数字工具栏按钮 ![image:23F__Program_Files_LyX20_bin____Resources_images_dialog-show_mathmatrix.png](http://blog.sciencenet.cn/static/js/grey.gif) ，出现的对话框将允许你设置要输入的矩阵的行数和列数，现在分别将其设为 2 和 3。LyX 将会插入一个 2 × 3 的矩阵，你可以在其中的 6 个输入点上输入任何公式，当然将它们留空也是可以的。

可以使用 Tab 键或方向键在矩阵各元素的输入点之间切换，赶快去试试它们的功能吧。

你还可以使用菜单 Edit⇒Rows & Columns 或数学工具栏按钮 ![image:24F__Program_Files_LyX20_bin____Resources_images_tabular-feature_append-row.png](http://blog.sciencenet.cn/static/js/grey.gif) 、![image:25F__Program_Files_LyX20_bin____Resources_images_tabular-feature_delete-row.png](http://blog.sciencenet.cn/static/js/grey.gif) 、![image:26F__Program_Files_LyX20_bin____Resources_images_tabular-feature_append-column.png](http://blog.sciencenet.cn/static/js/grey.gif) 和 ![image:27F__Program_Files_LyX20_bin____Resources_images_tabular-feature_delete-column.png](http://blog.sciencenet.cn/static/js/grey.gif) 改变矩阵的维数。

有关矩阵各列的水平对齐方式和整个矩阵的垂直对齐方式的更多信息请看 *User's Guide。注意：想要输入一个包含文字的表格时，请使用 LyX 强大的表格功能，而不要使用矩阵。*

### 4.4.6 显示模式

LyX 中公式的显示方式有两种，一种是行内公式，一种是单行公式。行内公式适合于较简短的公式，单行公式适合于较庞大的公式或是你想把它单独显示。另外，多行公式必需是单行公式，而且只有单行公式才能加标签和编号（参见 *User's Guide*）。

点击按钮 ![image:28F__Program_Files_LyX20_bin____Resources_images_math-display.png](http://blog.sciencenet.cn/static/js/grey.gif) 会插入一个单行公式，该公式新起一行并居中显示。按钮 ![image:28F__Program_Files_LyX20_bin____Resources_images_math-display.png](http://blog.sciencenet.cn/static/js/grey.gif) 其实是一个切换开关，点击它你会在公式的两种显示模式间切换。

单行公式和行内公式在显示上大致是相同的，你需要注意以下几点不同：

-   几个符号的默认字体变大，如： ∑ 和 ∫ 。
-   极限和求和的上下标被放在了符号的顶部和底部。
-   公式居中对齐。

关于单行公式最后一个需要注意的问题是排版问题。你需要确切的知道，单行公式和其前后的文字是不是在同一段中。如果你在单行公式后敲回车，那么它后边的文字将是新的一段，而新起一段是有段间距和缩进的。如果你不想新起一段，那么直接在单行公式后边输入文字就好了。

练习：将 example_raw.lyx 中的公式改为单行公式，看看有什么不同。



练习：使用本节学到的知识输入下边公式

 

**3**

 

：

 

f⁡(x)={

 

log

 

8

 

x

 

x>0

 

0

 

x=0

 

∑

 

i=1

 

5

 

α

 

i

 

+

 

\-

 

1

 

x

 

x<0

 

.

## 4.5 继续学习

LyX 的公式编辑器能做很多事情，现在你只是刚刚熟悉了最基本的。继续阅读 *User's Guide*，你可以学到：

-   给公式添加标签、编号。
-   多行公式。
-   改变字型。
-   细调字体大小与间距（草稿的最后阶段再考虑这些事）。
-   编辑宏。在文档开头处编写好后，文档中任何地方都可以使用。
-   其它。

# Chapter 5 杂项

## 5.1 LyX 的其它重要特性

我们并没有把 LyX 的所有都说全，也没有这样的打算。你可以查看 *User's Guide* 和 *Embedded Objects* 获得更多信息。这里我们将提到几个 LyX 的重要特性：

-   LyX 具有所见即所想的表格支持。使用菜单 Insert⇒Table 或 按钮 ![image:29F__Program_Files_LyX20_bin____Resources_images_tabular-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) 可以插入表格。在表格上单击右键，在右键菜单中选择表格设置对话框可以编辑表格的更多属性。
-   LyX 可以支持各种格式的图片。点击菜单 Insert⇒Graphics 或工具栏按钮 ![image:30F__Program_Files_LyX20_bin____Resources_images_dialog-show-new-inset_graphics.png](http://blog.sciencenet.cn/static/js/grey.gif) ，选择图片文件，你还可以对它旋转、缩放。你还可以对图表使用标题，LyX 还能自动产生图表的列表。
-   LyX 有很强的可定制性，从界面外观到文档的输出方式都可以通过几种方式来定制。大多的定制可以通过菜单 Tools⇒Preferences 来实现。更多信息参见菜单 Help⇒Customization。
-   LyX 开发组成员来自五大洲，所以 LyX 能比其它字处理软件更好的支持非英语（如荷兰语、德语、法语、希腊语、捷克语、土耳其语）。从右到左的语言：阿拉伯语、波斯语、希伯来语；亚洲语言：中文、日语、韩语等都能得到支持。你可以使用其它的语言写文档，也可以将 LyX 的界面和错误信息定义成其它的语言。
-   LyX 的菜单支持快捷键绑定。你既可以通过 Alt+F O 实现菜单 File⇒Open 的点击效果，也可以通过快捷键来实现（默认是 Ctrl+O）。快捷键绑定也是可以自定义的，更多信息参见菜单 Help⇒Customization。
-   LyX 可以读取 LaTeX 文档。参见 [5.2.2](file:///C:/Documents%20and%20Settings/Administrator/Local%20Settings/Temp/lyx_tmpdir.Hp3984/lyx_tmpbuf7/Tutorial.xhtml#sub_tex2lyx)。
-   LyX 支持拼写检查、同义词典和字数统计。
-   LyX 支持附录和集注。

## 5.2 LaTeX 用户必读

如果你对 LaTeX 一无所知，那么你可以跳过这一节。如果你想了解一点 LaTeX 相关的东西，那就继续读下去吧。很多使用 LyX 的人都对 LaTeX 比较熟悉，如果你也是这种人的话，你可能会有个疑问：LyX 真的能做到所有 LaTeX 能做的事情吗？LyX 的确能够通过这样或那样的方式做到 LaTeX 能做的所有事情，而且 LyX 还能大大简化编辑 LaTeX 文档的工作量。

由于本教程仅仅是一个入门指南，所以我们只将注意力集中在新手们关心的地方。为了缩短篇幅，我们只给出了最少的信息。在 *Additional Features* 和 *Embedded Objects* 中有 LyX 和 LaTeX 区别的大量信息，那里还将教你如何在 LyX 中玩各种 LaTeX 的花活儿。

### 5.2.1 TeX 模式

选择菜单 Insert⇒TeX Code 或工具栏按钮 ![image:31F__Program_Files_LyX20_bin____Resources_images_ert-insert.png](http://blog.sciencenet.cn/static/js/grey.gif) 进入 TeX 模式。在 TeX 模式下输入的所有东西都会用红色显示，并直接送给 LaTeX 编译处理。

数学公式中 TeX 模式处理起来稍有不同，这里键入“\”进入 TeX 模式，输入空格或非字母字符（如：数字、下划线、脱字号或括号）退出 TeX 模式。退出 TeX 模式时，如果 LyX 认识你输入的 TeX 命令，它就会将之转化为编译后的样子。如果你输入了“\gamma”并按下空格，LyX 会把它转化为蓝色的“ γ ”。对于不复杂的数学宏命令，LyX 都能转化成功的。对于熟练的 LaTeX 用户来说，直接输入 TeX 命令的方式会比使用数学工具栏速度快。

如果在 TeX 模式下输入“{”，LyX 将输入左右两个括号、退出 TeX 模式并将光标定位在两个括号中间等待输入。这使输入带参数的命令非常方便。

LyX 不能支持所有的 LaTeX 功能。有些根本就不支持，有些能够支持但不能实现所见即所想。TeX 模式使用户能够得到全部 LaTeX 的强大功能，而且还能使用 LyX 的方便特性（如：所见即所想的数学公式、表格和编辑方式）。LyX 永远也不会支持所有的 LaTeX 包，但你可以在序言加入 \usepackage{foo}（见 [5.2.4.2](file:///C:/Documents%20and%20Settings/Administrator/Local%20Settings/Temp/lyx_tmpdir.Hp3984/lyx_tmpbuf7/Tutorial.xhtml#sub_____________)），这样你就可以使用所有 LaTeX 包了。当然这些包并没有所见即所想支持。

### 5.2.2 导入 LaTeX 文档── tex2lyx

使用菜单 File⇒Import⇒LaTeX (plain) 导入 LaTeX 文档，程序将执行 tex2lyx，从 foo.tex 创建 foo.lyx，然后打开它。如果转换不成功，你可以试试在命令行加参数执行 tex2lyx 命令。

tex2lyx 能够转换大部份 LaTeX 文档，但不是所有东西都转换。它会把不懂的部分保留为 TeX 形式，所以你需要再进行手动修改。

tex2lyx 有自己的 manpage。阅读它找到不能被支持的命令、bugs 及其解决方法还有如何使用命令选项。

### 5.2.3 将 LyX 文档转化为 LaTeX 文档

选择菜单 File⇒Export⇒LaTeX 将你正在编辑的文档 whatever.lyx 输出为 whatever.tex。

### 5.2.4 LaTeX 序言

#### 5.2.4.1 文档类



Document⇒Settings 对话框中的 Document Class 页面能够处理很多 \documentclass 命令选项。这里你能够修改文档类、默认字体、页面大小，还可以在 Class options 区域中输入额外的选项

 

**1**

 

。

#### 5.2.4.2 其它序言

在 LaTeX 文档中输入的特殊命令在 LyX 当然也能使用。选择 Document⇒Settings⇒LaTeX Preamble，在对话框中输入命令即可，输入的任何东西都会直接传给 LaTeX 编译处理。

### 5.2.5 BibTeX

使用 BibTeX 可以创建供多文档使用的文献数据库……没错，LyX 能够支持 BibTeX。选择 Insert⇒List / TOC⇒BibTeX Bibliography 加入一个 BibTeX 文件，在数据库字段填入 BibTeX 文件名，在样式字段填入 BibTeX 样式文件名。

这时你就可以引用参考文献了（见 [3.6](file:///C:/Documents%20and%20Settings/Administrator/Local%20Settings/Temp/lyx_tmpdir.Hp3984/lyx_tmpbuf7/Tutorial.xhtml#sec_____________)）。LyX 会自动管理 BibTeX 的运行。引用对话框中将会显示你 BibTeX 文件中所有可用的引用项列表。

## 5.3 错误！

编译文档时，如果有 LyX 或 LaTeX 不能识别的东西，LyX 将会报错。这时会出现 LaTeX 错误对话框，点击某个错误将会定位到 LyX 文档中发生错误的地方，并显示详细 LaTeX 错误信息。