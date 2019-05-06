# Archlinux设置显卡驱动

一直没有意识到自己用Linux的时候使用的是CPU软解，这会使得播放视频时系统功耗较大，且容易造成卡顿。

为了使用显卡提供的硬件加速功能，让显卡来暴力运算，需要安装对应的驱动并做设置。这里记录以下过程。

由于我的Linux系统经常移动使用，我决定使用Intel集成显卡的驱动。

首先安装驱动：

*注：根据[这里](https://wiki.archlinux.org/index.php/Hardware_video_acceleration)，我的笔记本上安装这个就可以*

```bash
yay -S intel-media-driver
```



See [Wiki-HardwareAcceleration](https://wiki.archlinux.org/index.php/Hardware_video_acceleration)

```bash
export LIBVA_DRIVER_NAME=iHD
#LIBVA_DRIVER_NAME

grep -i vdpau /var/log/Xorg.0.log
#查看VDPAU_DRIVER=<???>
export VDPAU_DRIVER=va_gl

#export LIBVA_DRIVER_NAME=i965时使用下面这个命令验证
vainfo --display drm --device /dev/dri/renderD129
```

**实际上不设置LIBVA_DRIVER_NAME反而能够通过vaapi-copy运行硬件加速……**



对应MPV，这样可以开启硬件加速

```bash
mpv OS_TH --vo=gpu --hwdec=vaapi
#不要使用--vo=vaapi， 具体请参阅man mpv
```

