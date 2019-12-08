# CS350 review notes and code samples

## About

This repo was created to collect and share important Operating System concepts from the cs350 course offered at the University of Waterloo :mortar_board:. Feel free to contribute anything else!

## Study Topics

#### [Unit 1: Threads](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/threads-1up.pdf)

* Define Thread
* 5 reasons why use threads?
  * Resource Utilization
  * Parallelism
  * Responsiveness
  * Priority
  * Modularization
* 3 ways to implement concurrent threads
  * Hardware Support
  * Timesharing
  * Hardware + Timesharing
* Define Timesharing
* Define Context Switch
* Define Interrupts
* Define Preemption
* 4 ways to cause context switching
  * Thread_yield (voluntary)
  * Thread_exit (voluntary)
  * Thread blocks following Wchan_sleep() (volunatry)
  * Thread preempted (involuntary)
* 3 thread states
  * Running (on CPU)
  * Blocked (on wait channels)
  * Ready (waiting to run on CPU)
* Know how to draw 2 thread stacks with context switches between them

#### [Unit 2: Syncronization](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/synchronization-1up.pdf)

* Define Critical Sections
* Define Race Conditions
* Define Mutual Exclusion and how to achieve
* Define Test-and-Set and atomic operations
* __4 synchronization primitives__
  * __Spinlocks__
  * __Blocking Locks__
  * __Semaphores__
    * __Binary Semaphore__
    * __Counting Semaphore__
    * __Barrier Semaphore__
  * __Condition Variables__
    * What are mesa-style condition variables? How are they different from Hoare style?
* Deadlocks and techniques for prevention
  * __No Hold and Wait__
  * __Resource Ordering__
* Volatile keyword and how it works

#### [Unit 3: Processes, Kernel, System Calls](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/processes-1up.pdf)

* Define Process
* Define Kernel
* Define System Call
* Know how to use basic system calls
  * fork
  * getpid
  * waitpid
  * exit
  * execv
* Define Application Binary Interface (ABI)
* Distinguish between privileged and unprivileged code
* 2 things which make kernel code execute
  * __Interrupts__
  * __Exceptions__
* Define Interrupt Handler
* Define Exception Handler
* Distinguish between user (application) and kernel stack
* __Know how to draw processes and system calls with details regarding user and kernel stack__

#### [Unit 4: Virtual Memory](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/virtualmemory-1up.pdf)
* Define physical memory
* Define virtual memory and why we need it
* Memory structure, internal/external fragmentation
* Understand address translation and 3 ways to do it
  * __Dynamic relocation__
  * __Segmentation__
     * __Relocation Register + Limit register__
     * __Segment table__
  * __Paging__
     * __Single Level paging__
     * __Multi-Level paging__
* Understand the role of MMU in address translation
* Define Translation Lookaside Buffer (TLB)
  * Define __software-managed TLB__
  * Define __hardware-managed TLB__
  * Know about what each of the 64 bits in TLB is used for
* Undestand Virtual Memory implementation in OS/161 and its limitations
* Be able to translate virtual addresses to physical addresses using OS/161 
* Define Executable Linking Format (ELF) files and their role
  * Understand difference between __text segment__ and __data segment__ in OS/161 ELF files
* Undertand how virtual memory partitioned
  * User addresses from 0x0 to 0x7FFFFFFF
  * Kernel addresses from 0x80000000 to 0xFFFFFFFF
    * kseg0 - 0x80000000 to 0xA0000000 - 512mb - for kernel data structures, stacks, etc
    * kseg1 - 0xA0000000 to 0xC0000000 - 512mb - for addressing devices
    * kseg2 - 0xC0000000 to 0xFFFFFFFF - 512mb - unused
  * Know how to translate kernel virtual addresses to physical addresses
* Define __page swapping__ and how it is implemented
  * Define resident set
  * Define present bit
* Know why __page faults__ happen
* Know about __page replacement policies__
  * FIFO
  * Optimal
  * LRU
  * __Clock Replacement*__
* Define __locality__
  * __temporal locality__
  * __spatial locality__

#### [Unit 5: Scheduling](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/scheduling-1up.pdf)
* Define __Scheduling__ and understand why it's needed
  * Define __response time__
  * Define __turnaround time__
* Understand different scheduling implementations
  * __First come, first serve (FCFC)__
  * __Round Robin__
  * __Shortest Job First__
  * __Shortet Remaining Time First__
  * __Multi-level Feedback Queue (MLFQ)*__ 
  * __Linux Completely Fair Scheduler (CFS)*__
* Know 2 different ways of scheduling on Multi-Core processors
* Define __Scalabilility__
* Define __Cache Affinity__
* Define __Load Balancing__

#### [Unit 6: Devices and I/O](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/io-1up.pdf)
* Define device
* Define bus
  * Define internal bus
  * Define peripheral
* Define bridge
* Define device register and name 3 types
  * __Status device register__
  * __Command device register__
  * __Data device register__
* Define device driver
* Define polling and how to avoid
* Understand how device drivers can access device registers
  * Small data transfer
    * __Port-mapped I/O__
    * __Memory-mapped I/O__
  * Large data transfer
    * __Program-controlled I/O__
    * __Direct memory access (DMA)*__
* High level understanding of common persistent storage devices
  * Magnetic drums
  * Hard disks
  * SSD
  * Peristant RAM
* Know how to calculate cost of __hard disk I/O__
  * Calculate __seek time__
  * Calculate __rotational latency__
  * Calculate __transfer time__
  * __Request Service time = seek time + rotational latency + transfer time__
* Distinguish between sequential and non-sequential I/O
* Understand different __disk head scheduling__ algorithms
  * __First come first serve (FCFC)__
  * __Shortest Seek Time First (SSTF)__
  * __Elevator Algorithms (SCAN)*__
* Basic knowledge of how SSD's work

#### [Unit 7: File Systems](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/filesystems-1up.pdf)
* Define file
* Define file system
  * Define logical file system
  * Define virtual file system
  * Define physical file system
 * Understand basic file operations
   * Open
   * Close
   * Read, write, seek
   * Get, set
 * Define directory
 * Define i-number and i-node
 * Define hard link
 * Define mounting
 * Understand implementation of Very Simple File System (VSFS)
 * Define superblock
 * Calculate total space used given file name and inode structure
 * Calculate total number of reads and writes on inodes for file operations
 * Define chaining
 * Define external chaining
 * Understand where problems can arise in file operations and how to be fault tolerant
 * Define journaling file system

#### [Unit 8: Virtual Machines](https://www.student.cs.uwaterloo.ca/~cs350/F19/notes/wrapup-1up.pdf)
* Define virtual machine
* Define hypervisor
  * Define Type 1 Hypervisor
  * Define Type 2 Hypervisor
* Explain how virtual machine differs from regular machine in terms of
  * Privilege
  * Virtual memory
  * Page tables
  * I/O and devices

## Guides
 1. [LL and SC](Guides/LLSCMIPS.pdf)
 2. [Context Switch](Guides/Context_Switches_and_Switchframe.pdf)
 3. [Locks](Guides/Lock_Guide.pdf)
 4. [Condition Variable](Guides/Condition_Variable_Guide.pdf)
 5. [Virtual Memory](Guides/Virtual_Memory_Guide.pdf)
 6. [Disk and Devices](Guides/Disk_Guide.pdf)
 7. [File System](Guides/File_System_Guide.pdf)

## In-class Handouts
 1. [Threads](Handouts/Threads/)
 2. [Synchronization](Handouts/Synchronization/)
 3. [Processes](Handouts/Processes/)
 4. [Virtual Memory](Handouts/Virtual%20Memory/)
 5. [File Systems](/Handouts/File%20Systems/)

## Extra Review
* Recent Midterms - See piazza.
* [Past Midterm Exams](https://www.student.cs.uwaterloo.ca/~cs350/common/old-exams/)
* [Review Questions Compiled by W10 Students](https://www.student.cs.uwaterloo.ca/~cs350/common/review-questions/CS350-course-review.pdf)

## Credits

A big thank you to my Professor __Lesley Istead__ for dedicating her time to teaching this epic course and personally setting all her students up for success. I especially appreciate her initiative and effort to stream her lectures to all students this term.
