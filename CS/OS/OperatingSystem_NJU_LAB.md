# OperatingSystem_NJU_LAB

## Info

助教：徐圣斌 kingxu@smail.nju.edu.cn

课程网站：114.212.80.195:8170/2019oslab

## Lab1 系统引导

CS：IP

## Lab2 系统调用

## Lab3 进程切换

## Lab4 并发控制

## Lab5 文件系统



## 其他基础知识

## Makefile

[中文blog](https://www.kancloud.cn/kancloud/make-command/45594)

### 变量赋值

### 懒人专属

```
VARIABLE = value
```

变量的正常设置 - 当使用变量时，不会在声明变量时递归地扩展变量中的值

### 立即设定

```
VARIABLE := value
```

通过简单扩展内部值来设置变量 - 其中的值在声明时间扩展。

### 设置如果缺席

```
VARIABLE ?= value
```

仅在变量没有值时设置变量

### 附加

```
VARIABLE += value
```