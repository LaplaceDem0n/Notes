# OSTEP

# 虚拟化（Virtualization）

## 进程抽象-Chapter 3-6

以下程序将输出多少个Hello？

```c
for (int i = 0; i < n; i++) {
    fork();  
    printf("Hello\n");
}
```

## 终端与Shell

有点意思，大班不考。

[Job Control](https://www.gnu.org/software/libc/manual/html_node/Job-Control.html)

 [Implementing a Shell](https://www.gnu.org/software/libc/manual/html_node/Implementing-a-Shell.html#Implementing-a-Shell)

## 处理器调度-Chapter 6-10

## 虚存抽象-Chapter 13-20

只允许地址空间映射足够大的连续内存，并且可以设置访问权限

-   段 (segment)：仅允许几段连续的虚拟内存；

    O(S)*O*(*S*)

    开销

    -   x86: GDT, LDT描述“段”的内存映射

-   页 (page)：可以以页为单位自由映射；

    O(M/p)*O*(*M*/*p*)

    开销

    -   x86: “页目录-页表”数据结构描述内存映射
    -   内存越大，页表层数越多：PML4 (48bit)

-   复习：名词解释
    
    -   多级页表；反置页表；TLB (Translation Lookaside Buffer)



## 08-Cpu-Scheduling-mlfq

**Challenging problem:**

Response time Vs Turnaround time

MLFQ

### 31-Threads-sema

wait->P->try->decrease->down

post->V->??->increase->up

# 并发（Concurrency）

## 共享内存多进程-Chapter 25-27

**并发与并行：单处理器并发，多处理器才能并行。**

Don’t panic：

>   计算机系统为我们提供了同时保证顺序、原子性、可见性的同步操作——**互斥锁、条件变量、信号量、事务内存**……帮助程序员写出正确性容易保证的代码、实现并发控制。

### 并发的难点

*由并发性引起的bug非常难触发，触发了也难复现！！*

#### 顺序性 (order)

即源代码中的部分指令不再按顺序甚至不再出现。

可能被编译器优化了。

解决方式：[volatile](https://en.cppreference.com/w/c/language/volatile)或#**define** barrier() asm volatile ("":::"memory")

1.  关于volatile，区分以下几种写法：

>   ```c
>   volatile char *p;
>   char * volatile p;
>   volatile char * volatile p;
>   ```

2.  关于barrier可以这样用，可以阻止优化跨越边界，会生成两条独立的`add`指令。

>   ```c
>   void foo() {
>     x++;
>     barrier();
>     x++;
>   }
>   ```

#### 原子性(atomicity)

一段代码执行在多处理器上不被打断。

被操作系统和多处理器，缓存等构造影响而丧失——指令序列可以在任意时刻被中断，然后操作系统切换到其他线程执行。

解决方式：单CPU关中断，多CPU的信号量与管程，互斥锁保护临界区等。

#### 可见性 (visibility)

**在多个线程共享内存时，并发程序行为的准确建模是十分困难的**。

写入的值能被其他处理器正确读到。

因为缓存和乱序（计算器硬件）影响而丧失。

解决方式：需要指令集的帮助。

## 硬件眼中的操作系统

操作系统是“管理资源、服务应用”的程序。

-   Top-Down：操作系统 = 游戏规则
-   Bottom-Up：操作系统 = C程序 (x86-qemu为例)

Q: Spin lock 到底是什么？

## 互斥-Chapter 28

*大班所说的信号量初值为1的PV操作实际上可以看作互斥锁的特殊实现。*

Q：可重入 (Reentrance)性质为什么重要？

-   自旋会导致CPU浪费（busy waiting），且只适合短临界区。
    -   对于单CPU所有的自旋都是浪费的，不如关中断 = 顺序 + 原子性 + 可见性。这对于单处理器和短临界区非常好用。
    -   对于多CPU，同样只适合短临界区。
    -   对于长临界区，关中断是很危险的。
-   不如利用信号量或管程！

## 并发数据结构

Q：机制（mechanisms）和策略（policies）？？



## 同步-Chapter 29-30

**教材的条件变量和信号量讲得非常棒，因此请大家仔细阅读。**

所谓“同步”就是在某个时刻，两个线程达成共识，典型的场景：

-   NPY：等我洗个头就出门/等我打完这局游戏就来
-   舍友：等我写完这段代码就吃饭
-   导师：等我出差回来就讨论这个课题

**总起**

-   同步：生产者-消费者问题、哲学家吃饭问题
-   条件变量(condition variables, CV)
    -   **等待**某个条件满足后发生
    -   某个条件满足，**唤醒一个**正在等待的线程
    -   某个条件满足，**唤醒所有**正在等待的线程
    -   大班只讲了wait（CV）和signal（CV）
    -   *Note: signal可能丢失-当没有人在等待的时候就没有人被唤醒*
-   信号量与PV操作
    -   游泳池管理
    -   P(&sem) - prolaag = try + decrease; wait; down; in。等到一个手环后返回(如果此时有空闲的手环，立即返回)
    -   V(&sem) - verhoog = increase; post; up; out。创造一个手环
-   管程（服务生）与哲学家问题

关于信号量的更多解读：信号量 = 互斥锁 + 条件变量

-   P/V是原子操作
-   仅有一个手环 = 互斥锁
-   P = wait; V = signal
-   因为计数器的存在，不会发生signal“丢失”

## 并发bugs-Chapter 32

bugs分类：

-   死锁 (ABBA)
-   原子性违反 (ABA)
-   顺序违反 (BA)
-   数据竞争

### 死锁

——出现线程“互相等待”的情况，比如：

>   ```C
>   thread1      tread2
>   lock(A);
>                lock(B);
>   lock(B); // 阻塞
>                lock(A); // 阻塞
>   // 任何线程都不能进入临界区
>   ```

#### 死锁四条件 

([Edward G. Coffman](https://en.wikipedia.org/wiki/Edward_G._Coffman,_Jr.), 1971)

-   互斥：一个资源每次只能被一个进程使用
-   请求与保持：一个进程请求资阻塞时，不释放已获得的资源
-   不剥夺：进程已获得的资源不能强行剥夺
-   循环等待：若干进程之间形成头尾相接的循环等待资源关系

### 原子性/顺序违反

并发bug并不只局限于死锁。如果你在该使用锁保护临界区时没有正确的保护，这显然是个并发bug。并发的`sum++;`、`buf[pos++] = data;`处理不当都会导致bug，但显然它们都不是死锁。

除了死锁以外，最常见的就对应了`lock/unlock`和`wait/signal`使用错误。lock/unlock保护临界区的**原子性**，使用不当就导致原子性违反(atomicity violation, AV)；而wait/signal维护事件之间的顺序，使用不当就导致顺序违反(order violation, OV)。

回顾我们实现并发控制的工具

-   互斥锁(lock/unlock) - 原子性。忘记上锁——原子性违反 (Atomicity Violation, AV)。
-   条件变量(wait/signal) - 同步。忘记同步——顺序违反 (Order Violation, OV)。

### 数据竞争

在并发bug中，有一类很重要的问题是**数据竞争(data race)**，**数据竞争**是两个共享内存访问，它们满足以下条件：

-   访问同一个共享内存变量；
-   发生在不同的线程；
-   至少有一个是写。

>   **数据竞争**意味着存在**线程间的数据流**，并且这个数据流极有可能是程序员没有考虑到的，例如以下例子：
>
>   ```
>   if (node->fd != -1) {
>                                node->fd = -1; // 另一个线程
>     write(node->fd, ...);
>   }
>   ```

# Reading notes for concurrency

## 26简介

### 26-0内存空间布局

描述了多线程内存程序的内存空间布局，它们会有多个分布的stack。

### 26-1为什么是线程

1.  线程能够并行，利用现代处理器多核心多线程的特点
2.  避免由于低速IO阻塞程序，正如批处理系统上的多道程序设计能在一个不同程序的进程间切换那样。
3.  线程比进程更轻量化
4.  线程间共享内存地址，所以更容易共享数据

### 26-2并发问题

1.  例程1:不加控制时，**顺序**得不到保证。
2.  例程2:CPU的中断机制使得**原子性**得不到保证。

### 26-3共享数据问题

**可见性**丧失。

### 26-4问题核心与解决方法

失控的调度序列与互斥锁。

### 26-5对原子性的期待

任意操作的原子性的机器级指令都有实现是不现实的，作为代替，系统提供了一系列同步原语。

## 26-6“我睡了，等会儿你叫我”

这样的机制在条件变量（CV）中实现。

### 26-7为什么OS课要学这个？

OS本身就是一个并发程序，尤其是引入了中断之后。

很多OS kernel中的数据结构更新都需要顺序、原子性、可见性。

## 27线程API

实际做Lab都会用。

## 28锁

### 28-5控制中断

**本节主要聚焦于如何实现Lock。**

在单处理器上关中断可以很简单地保证原子性，但存在很多缺点：

1.  这样的操作意味这系统需要给每一个程序都赋予开关系统中断的权力，如果程序员设计不当或存在恶意程序，都可能对系统造成危害。
    1.  lock()后程序进入了死循环。
    2.  程序一开始就lock()，快结束了才unlock()。
2.  对于多处理器不起作用，其他处理器上的线程依然可以访问变量。
3.  对于长临界区，可能导致中断被忽略。这会带来严重的问题，如磁盘读完了，OS却忽略了磁盘产生的中断……那么等读磁盘的程序将永远沉睡。
4.  开关中断对现代处理器来说是比较慢的操作。

*对于单处理器系统，在Kernel内的代码，用起来还不错。*



### 28-7机器级指令实现自旋锁

这里的机器级指令就是Test&Set(Atomic exchange)。

**Test** the *flag*, and **set** its value to *whatever you want*.

### 28-8评价自旋锁

-   **证明正确性？**，是的，自旋锁提供了互斥性。同一时刻只能有一个线程进入临界区。
-   并**不公平**，一切都靠运气。
-   性能：单核上就是智障，多核多线程还可以接受。

### 28-9-11另外一种，又一种，YA机器指令的实现

1.  Compare&Swap
2.  Load-linked&Store-Conditional
3.  Fetch&Add

**Skipped**

### 28-12-13别busy waitng了！

>    Just Yield，Baby！

### 28-14拒绝饥饿

## 30条件变量（CV）

**skipped.**

## 31信号量（Semaphore）

**太难受了这一部分打印出来看吧，程序好多。**

# XF并发进程

无关并发进程的判断与Bernstein条件。

# 持久化（Persistence）

## 存储介质-Chapter 37, 44

科普信息，不过作为CS同学还是可以看一看的。

## I/O设备与驱动-Chapter 36

设备是三种操作的集合

-   发送命令、读取状态、传输数据

CPU终究是通过地址和数据访问I/O设备的

-   Port IO/MMIO只是两种不同的地址空间
-   电路负责根据地址把地址和数据“转发”给设备

CPU使用设备的流程

-   给设备发送命令 (指令数量较少，因此相对较快)
-   → 传送数据 (数据量大时非常耗时)
-   → 等待设备完成 (设备与CPU并行)

设备驱动程序把I/O设备控制接口抽象为一组API

-   设备最常用的功能是交换数据：read/write、配置：ioctl

Direct Memory Access(DMA)，可以理解为实现`memcpy()`的I/O设备

-   内存-内存、端口-内存的复制
-   这样CPU就可以在传送数据时做其他事

## 文件系统概念与API-Chapter 39

虚拟，抽象，便于用户使用

对同一个文件的多次操作是自然的

-   文件描述符避免了每次操作都要重新打开文件
-   同时也帮助我们自动管理文件访问的偏移量

概念：文件 = 虚拟磁盘 = `uint8_t file[]`

------

内存映射方式访问

-   适合随机访问的结构数据 (数据库)

```c
fd = open("/dev/sda", O_RDONLY);
uint8_t *file = mmap(NULL, 128 GB, PROT_READ | 					 PROT_WRITE,MAP_SHARED, fd, 0);
```

------

read/write方式访问

-   适合流式文件 (文件描述符托管了offset)

```c
int fd = open("fname", O_WRONLY);
write(fd, "Hello ", 6);
write(fd, "World\n", 6);
```

## 文件系统实现-Chapter 37 40

Block I/O调度，I/O请求优化 + 兼顾进程优先级和公平

-   例子：按照“电梯”方式寻道

这件事不该归操作系统管

-   磁盘的读/写特性差异太大了
    -   SSD vs. HDD vs. USB Flash
    -   每个磁盘的内部特性又不同，需要不同参数
-   应该是磁盘里的系统管(毕竟它最懂磁盘的性能)

操作系统管什么？

-   桌面系统：保证进程尽可能公平地获得I/O操作(类似CFS)
-   服务器/虚拟化环境：只做请求优化，不做额外的调度(FIFO)

实现文件系统需要考虑以下因素：

-   虚拟磁盘的数据结构 (链表、树、……)
-   目录文件的数据结构
-   inode的表示和存储
-   balloc/bfree的实现

## FAT和ext2-Chapter 40

File Allocation Table

看书吧。

## 持久数据的可靠性-Chapter 38

## 崩溃恢复与日志-Chapter 42, 43

大班没教，暑假再补吧。

