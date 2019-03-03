# LaTeX on Archlinux

## 安装过程

安装`Tex`包与`VScode`。

```bash
sudo pacman -S texlive-latexmost texlive-langchinese texlive-latexextra 
sudo pacman -S visual-studio-code-bin
```



## 配置过程

在VScode拓展商店中安装`LaTeX Workshop`。

在VScode设置文件中粘贴以下部分，可保存时自动编译。

**Tips:该配置文件默认使用了ttf-dejavu-sans-mono-powerline-git字体。**

```json
{
    "window.zoomLevel": 2,
    "editor.fontSize": 17,
    "editor.fontFamily": "'Dejavu Sans Mono for Powerline', 'monospace'",

    "latex-workshop.latex.recipes": [
        {
          "name": "xelatex",
          "tools": ["xelatex"]
        }
      ],
      "latex-workshop.latex.tools": [
        {
          "name": "xelatex",
          "command": "xelatex",
          "args": [
            "%DOC%.tex"
          ]
        }
    ],
    "latex-workshop.view.pdf.viewer": "tab"
}
```



## 学习过程

[Archlinux‘s wiki on TeX Live](https://wiki.archlinux.org/index.php/TeX_Live_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)#%E4%B8%AD%E6%96%87%E5%8C%96)

[一份其实好吃的 LaTeX 入门餐](https://blog.joway.io/posts/latex/)

[一份其实很短的 LaTeX 入门文档](https://liam.page/2014/09/08/latex-introduction/#%E4%BC%98%E9%9B%85%E7%9A%84_LaTeX)

[VScode插件使用wiki](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install#usage)

[VScode插件github主页](https://github.com/James-Yu/LaTeX-Workshop)

[比较老但是播放量很高的油管教程](https://www.youtube.com/watch?v=rVt_hponBW4)



## 实用模板

[Homework](https://github.com/jdavis/latex-homework-template)

[Tsinghua University’s template](https://ctan.math.illinois.edu/macros/latex/contrib/thucoursework/thucoursework.pdf)

[一个符合中文排版要求的 LaTeX 样式模板](https://github.com/joway/latex-template-zh)



## 参考资料

[LaTeX wiki](https://en.wikibooks.org/wiki/LaTeX)

[公式在线识别](http://detexify.kirelabs.org/classify.html)



## 论坛

[CTAN](https://www.ctan.org/search/#byDescription)



## 在Arch上遇到的bug

### 现象

打开本地文档时报错：

```
➜  ~  texdoc texdoc
➜  ~  /usr/share/texmf-dist/scripts/texdoc/search.t..."]:569: assertion failed!"
```



### 原因

问题在于texdoc v3（文件/usr/share/texmf-dist/scripts/texdoc/search.tlu）本身，因为init_tlp_database（第434行）试图访问“//tlpkg/texlive.tlpdb”。这条道路显然是错误的。发生这种情况是因为get_tlroot（第405行）引用了SELFAUTOPARENT kpsewhich变量，无论哪个原因，它都等于Arch上的“/”。这可以通过$（kpsewhich --var-value SELFAUTOPARENT）确认。

[ref1](https://bugs.archlinux.org/task/60013)

[ref2](https://www.linuxquestions.org/questions/slackware-14/texlive-texdoc-not-working-4175634089/#post5882128)



### 解决方案

```bash
su -
mkdir /tlpkg
wget -O /tlpkg/texlive.tlpdb http://tug.ctan.org/systems/texlive/tlnet/tlpkg/texlive.tlpdb
texdoc -DlM texlive-en |& grep cache-tlpdb.lua
mv /root/.texlive2018/texmf-var/texdoc/cache-tlpdb.lua \
  /usr/share/texmf-dist/scripts/texdoc/Data.tlpdb.lua
mktexlsr
```





## 其他走过的弯路

为了使用自动编号，并将标号放在文字的右侧。STFW,RTFM耗时3小时……

在Archlinux下安装文档包后可以用`texdoc xxx`的方式查阅`xxx`这个宏包对应的使用手册。

[LaTeX使用titlesec宏包改变章节编号形式的方法](https://www.bbsmax.com/A/D854VGYvzE/)

