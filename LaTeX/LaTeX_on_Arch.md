# LaTex on Archlinux

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



[一个符合中文排版要求的 LaTeX 样式模板](https://github.com/joway/latex-template-zh)



[VScode插件使用wiki](https://github.com/James-Yu/LaTeX-Workshop/wiki/Install#usage)

[VScode插件github主页](https://github.com/James-Yu/LaTeX-Workshop)



[比较老但是播放量很高的油管教程](https://www.youtube.com/watch?v=rVt_hponBW4)



## 实用模板

[Homework](https://github.com/jdavis/latex-homework-template)

[Tsinghua University’s template](https://ctan.math.illinois.edu/macros/latex/contrib/thucoursework/thucoursework.pdf)



## 参考资料

[LaTeX wiki](https://en.wikibooks.org/wiki/LaTeX)

