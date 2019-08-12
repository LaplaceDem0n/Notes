# Bash scirpt

**目标**

1. 使用变量灵活地设置（交互式）
2. 尽量只跑一次

## 具体实现

*可以利用虚拟机的快照功能来进行实验！！*

1. Install（LUKS enable or not）
   1. 流程控制
   2. 变量调整
   3. 文字流处理
2. 基本软件配置
   1. Chrome，yay，v2ray等
   2. i3和其他dotfiles可以管理的一切配置等
3. 个人文件同步
   1. Dropbox，Chrome同步等
   2. dotfiles无法直接管理的一切配置等（GUI程序的Proxy，Encoding之类问题）。
4. 模板化添加新软件配置
   1. 软件名称？安装方法？
   2. 注意事项？
   3. 使用时配置？
5. 如何把上面这很多行的脚本统一管理起来？