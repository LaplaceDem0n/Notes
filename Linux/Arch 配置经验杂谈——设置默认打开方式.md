# Arch 配置经验杂谈——设置默认打开方式

引言：使用ArchLinux有了一段时间后，有一点比较不爽，就是从网上下载的文件，使用，show in folder或者open file，都是使用chrome自己打开的。

咨询了同事，又加上自己的一段时间摸索，终于找到如何设值了。

原来在archlinux下，所有的程序安装都会生成一个像windows快捷方式的文件，这个目录在我的archlinux下

`/usr/share/applications` 目录下，可以看到很多以扩展名为desktop的文件，这些文件可以用vim进行打开。

关于文件的具体说明：<http://www.ibm.com/developerworks/cn/linux/l-cn-dtef/> 

当前每个文件格式默认关联的程序内容放在：`~/.local/share/applications/defaults.list`，他的内容格式是：

 

`application/pdf=xpdf.desktop`

 对应的内容就是：

  `mime-type= [desktop文件]`

 上面的内容格式意思是linux下默认打开的pdf文件使用xpdf软件打开（当然前提需要你安装xpdf）

 

**案例一：**

 

1.希望xls文件，默认打开方式为libreoffice

linux下可以使用xdg-open file 的方式来打开文件，他会从当前桌面环境中找到默认程序进行打开，因为我是原生的awesome，没有使用任何de（desktop enviorment），比如gnome、kde，xfce4等。使用命令：

`xdg-mime query filetype some.xls`

输出：

`application/msword; charset=binary`  

前面的application/msword就是mimetype，再使用命令：

`xdg-mime query default application/msword` 

如果输出是空，代表当前尚未设置默认的文件打开程序，当使用命令：

`xdg-open some.xls`

将会调用当前环境的浏览器，比如firefox、opera、chrome中一个来打开，会使用先找到的工具进行操作，因为这时候我们想使用，libreoffice进行默认的word、excel文件的打开方式，所以可以使用命令：

`xdg-mime default libreoffice-writer.desktop application/msword`  

 设置，这时候你再使用，`xdg-open some.xls`，哈哈，是不是libreoffice启动了？



**案例二：**



chrome中当有下载文件时，选择show in folder的时候，默认打开的程序仍然是chrome浏览器。如果这时候我想用xfce4下的thunar打开怎么办呢？

操作步骤跟上面一样，先找到目录属于的mime-type是什么，然后设置对应的desktop文件就行了。

操作步骤：

```bash
xdg-mime query filetype /home/
xdg-mime query default inode/directory
xdg-mime default Thunar-folderhandler.desktop inode/directory 
```
