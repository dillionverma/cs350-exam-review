# CS350 review notes and code samples

## About

This repo was created to collect and share important Operating System concepts from the cs350 course offered at the University of Waterloo :mortar_board:. Feel free to contribute anything else!

## Study Topics

#### Unit 1: Threads

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

#### Unit 2: Syncronization

* Define Critical Sections
* Define Race Conditions
* Define Mutual Exclusion and how to achieve
* Define Test-and-Set and atomic operations
* __4 synchronization primitives__
  1. __Spinlocks__
  2. __Blocking Locks__
  3. __Semaphores__
     * __Binary Semaphore__
     * __Counting Semaphore__
     * __Barrier Semaphore__
     * What are mesa-style condition variables? How are they different from Hoare style?
  4. __Condition Variables__
* Deadlocks and techniques for prevention
    1. __No Hold and Wait__
    2. __Resource Ordering__
* Volatile keyword and how it works

#### Unit 3: Processes, Kernel, System Calls

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
  1. Interrupts
  2. Exceptions
* Define Interrupt Handler
* Define Exception Handler
* Distinguish between user (application) and kernel stack
* __Know how to draw processes and system calls with details regarding user and kernel stack__

#### Unit 4: Virtual Memory
* Define physical memory
* Define virtual memory and why we need it
* Understand address translation and 3 ways to do it
  1. __Dynamic relocation__
  2. __Segmentation__
     1. __Relocation Register + Limit register__
     2. __Segment table__
  3. __Paging__
     1. __Single Level paging__
     2. __Multi-Level paging__
* Understand the role of MMU in address translation

... more to be added soon

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
 4. [Virtual Memory](Handouts/Virtual\Memory/)
 5. [File Systems](/Handouts/File\Systems/)

## Extra Review
* [Past Midterm Exams](https://www.student.cs.uwaterloo.ca/~cs350/common/old-exams/)
* [Review Questions Compiled by W10 Students](https://www.student.cs.uwaterloo.ca/~cs350/common/review-questions/CS350-course-review.pdf)

## Credits

A big thank you to my Professor __Lesley Istead__ for dedicating her time to teaching this epic course and personally setting all her students up for success. I especially appreciate the initiative to streaming her lectures for all students across all sections.

