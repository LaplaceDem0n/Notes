# Operating System OSTEP 

# 虚拟化（Virtualization）

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

### 原子性(atomicity)

一段代码执行在多处理器上不被打断。

被操作系统和多处理器，缓存等构造影响而丧失——指令序列可以在任意时刻被中断，然后操作系统切换到其他线程执行。

解决方式：单CPU关中断，多CPU的信号量与管程，互斥锁保护临界区等。

### 可见性 (visibility)

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

# 持久化（Persistence）