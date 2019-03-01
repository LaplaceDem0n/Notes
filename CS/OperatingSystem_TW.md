# OperatingSystem_TW

## Process

### Exceptions & interrupts

CPU中的寄存器存着Vector Table的起始地址。

开机时填写异常处理的Vector Table，里面填写异常处理程序的开头地址，处理程序丢到内存里。 



### User stack & Kernel stack

切换Mode的时候同时换SP。保证Kernel信息的安全。



### Process creation & destroy in Linux

-   fork()
    -   differs from the parent only in its PID\PPID(Process ID\Parent Process ID) & certain resources
    -   copy-on-write
-   exec()
    -   loads a new executable into the address space & execute it
-   fork()+exec()=spawn()

## 

### Process descriptor in Linux

-   Store
    -   Store in memory, kernel space.
    -   Reason(in kernel):**Easy to access** the descriptor.
-   Create
    -   By “Parent”
    -   While(precisely “before”) the process is created
-   Destroy
    -   People destroy themselves, “anster” destroy their process descriptor
    -   After the process is ended
-   Finite State Machine
    -   Ready (waiting for CPU)
    -   Running (using CPU)
    -   Sleeping (waiting for IO)
    -   Zombie (just being forked or just die) 

### Details in process creation & destroy

-   User process/thread
-   Kernel process/thread