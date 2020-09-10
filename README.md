# CS350 review notes and code samples

## About

This repo was created to collect and share important Operating System concepts from the cs350 course offered at the University of Waterloo :mortar_board:. Feel free to contribute anything else!

## Study Topics

#### [Unit 1: Threads](Notes/threads-1up.pdf)

- Define Thread
- 5 reasons why use threads?
  - Resource Utilization
  - Parallelism
  - Responsiveness
  - Priority
  - Modularization
- 3 ways to implement concurrent threads
  - Hardware Support
  - Timesharing
  - Hardware + Timesharing
- Define Timesharing
- Define Context Switch
- Define Interrupts
- Define Preemption
- 4 ways to cause context switching
  - Thread_yield (voluntary)
  - Thread_exit (voluntary)
  - Thread blocks following Wchan_sleep() (volunatry)
  - Thread preempted (involuntary)
- 3 thread states
  - Running (on CPU)
  - Blocked (on wait channels)
  - Ready (waiting to run on CPU)
- Know how to draw 2 thread stacks with context switches between them

#### [Unit 2: Syncronization](Notes/synchronization-1up.pdf)

- Define Critical Sections
- Define Race Conditions
- Define Mutual Exclusion and how to achieve
- Define Test-and-Set and atomic operations
- **4 synchronization primitives**
  - **Spinlocks**
  - **Blocking Locks**
  - **Semaphores**
    - **Binary Semaphore**
    - **Counting Semaphore**
    - **Barrier Semaphore**
  - **Condition Variables**
    - What are mesa-style condition variables? How are they different from Hoare style?
- Deadlocks and techniques for prevention
  - **No Hold and Wait**
  - **Resource Ordering**
- Volatile keyword and how it works

#### [Unit 3: Processes, Kernel, System Calls](Notes/processes-1up.pdf)

- Define Process
- Define Kernel
- Define System Call
- Know how to use basic system calls
  - fork
  - getpid
  - waitpid
  - exit
  - execv
- Define Application Binary Interface (ABI)
- Distinguish between privileged and unprivileged code
- 2 things which make kernel code execute
  - **Interrupts**
  - **Exceptions**
- Define Interrupt Handler
- Define Exception Handler
- Distinguish between user (application) and kernel stack
- **Know how to draw processes and system calls with details regarding user and kernel stack**

#### [Unit 4: Virtual Memory](Notes/virtualmemory-1up.pdf)

- Define physical memory
- Define virtual memory and why we need it
- Memory structure, internal/external fragmentation
- Understand address translation and 3 ways to do it
  - **Dynamic relocation**
  - **Segmentation**
    - **Relocation Register + Limit register**
    - **Segment table**
  - **Paging**
    - **Single Level paging**
    - **Multi-Level paging**
- Understand the role of MMU in address translation
- Define Translation Lookaside Buffer (TLB)
  - Define **software-managed TLB**
  - Define **hardware-managed TLB**
  - Know about what each of the 64 bits in TLB is used for
- Undestand Virtual Memory implementation in OS/161 and its limitations
- Be able to translate virtual addresses to physical addresses using OS/161
- Define Executable Linking Format (ELF) files and their role
  - Understand difference between **text segment** and **data segment** in OS/161 ELF files
- Undertand how virtual memory partitioned
  - User addresses from 0x0 to 0x7FFFFFFF
  - Kernel addresses from 0x80000000 to 0xFFFFFFFF
    - kseg0 - 0x80000000 to 0xA0000000 - 512mb - for kernel data structures, stacks, etc
    - kseg1 - 0xA0000000 to 0xC0000000 - 512mb - for addressing devices
    - kseg2 - 0xC0000000 to 0xFFFFFFFF - 512mb - unused
  - Know how to translate kernel virtual addresses to physical addresses
- Define **page swapping** and how it is implemented
  - Define resident set
  - Define present bit
- Know why **page faults** happen
- Know about **page replacement policies**
  - FIFO
  - Optimal
  - LRU
  - **Clock Replacement\***
- Define **locality**
  - **temporal locality**
  - **spatial locality**

#### [Unit 5: Scheduling](Notes/scheduling-1up.pdf)

- Define **Scheduling** and understand why it's needed
  - Define **response time**
  - Define **turnaround time**
- Understand different scheduling implementations
  - **First come, first serve (FCFC)**
  - **Round Robin**
  - **Shortest Job First**
  - **Shortet Remaining Time First**
  - **Multi-level Feedback Queue (MLFQ)\***
  - **Linux Completely Fair Scheduler (CFS)\***
- Know 2 different ways of scheduling on Multi-Core processors
- Define **Scalabilility**
- Define **Cache Affinity**
- Define **Load Balancing**

#### [Unit 6: Devices and I/O](Notes/io-1up.pdf)

- Define device
- Define bus
  - Define internal bus
  - Define peripheral
- Define bridge
- Define device register and name 3 types
  - **Status device register**
  - **Command device register**
  - **Data device register**
- Define device driver
- Define polling and how to avoid
- Understand how device drivers can access device registers
  - Small data transfer
    - **Port-mapped I/O**
    - **Memory-mapped I/O**
  - Large data transfer
    - **Program-controlled I/O**
    - **Direct memory access (DMA)\***
- High level understanding of common persistent storage devices
  - Magnetic drums
  - Hard disks
  - SSD
  - Peristant RAM
- Know how to calculate cost of **hard disk I/O**
  - Calculate **seek time**
  - Calculate **rotational latency**
  - Calculate **transfer time**
  - **Request Service time = seek time + rotational latency + transfer time**
- Distinguish between sequential and non-sequential I/O
- Understand different **disk head scheduling** algorithms
  - **First come first serve (FCFC)**
  - **Shortest Seek Time First (SSTF)**
  - **Elevator Algorithms (SCAN)\***
- Basic knowledge of how SSD's work

#### [Unit 7: File Systems](Notes/filesystems-1up.pdf)

- Define file
- Define file system
  - Define logical file system
  - Define virtual file system
  - Define physical file system
- Understand basic file operations
  - Open
  - Close
  - Read, write, seek
  - Get, set
- Define directory
- Define i-number and i-node
- Define hard link
- Define mounting
- Understand implementation of Very Simple File System (VSFS)
- Define superblock
- Calculate total space used given file name and inode structure
- Calculate total number of reads and writes on inodes for file operations
- Define chaining
- Define external chaining
- Understand where problems can arise in file operations and how to be fault tolerant
- Define journaling file system

#### [Unit 8: Virtual Machines](Notes/wrapup-1up.pdf)

- Define virtual machine
- Define hypervisor
  - Define Type 1 Hypervisor
  - Define Type 2 Hypervisor
- Explain how virtual machine differs from regular machine in terms of
  - Privilege
  - Virtual memory
  - Page tables
  - I/O and devices

## Guides

1.  [Pointers](Guides/Pointers.pdf)
2.  [LL and SC](Guides/LLSCMIPS.pdf)
3.  [Context Switch](Guides/Context_Switches_and_Switchframe.pdf)
4.  [Locks](Guides/Lock_Guide.pdf)
5.  [Condition Variable](Guides/Condition_Variable_Guide.pdf)
6.  [Virtual Memory](Guides/Virtual_Memory_Guide.pdf)
7.  [Disk and Devices](Guides/Disk_Guide.pdf)
8.  [File System](Guides/File_System_Guide.pdf)

## In-class Handouts

1.  [Threads](Handouts/Threads/)
2.  [Synchronization](Handouts/Synchronization/)
3.  [Processes](Handouts/Processes/)
4.  [Virtual Memory](Handouts/Virtual%20Memory/)
5.  [File Systems](/Handouts/File%20Systems/)

## Extra Review

- Recent Midterms - See piazza.
- [Past Midterm Exams](https://www.student.cs.uwaterloo.ca/~cs350/common/old-exams/)
- [Review Questions Compiled by W10 Students](https://www.student.cs.uwaterloo.ca/~cs350/common/review-questions/CS350-course-review.pdf)

## Credits

A big thank you to my Professor **Lesley Istead** for dedicating her time to teaching this epic course and personally setting all her students up for success. I especially appreciate her initiative and effort to stream her lectures to all students this term.
