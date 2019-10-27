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
  * __Spinlocks__
  * __Blocking Locks__
  * __Semaphores__
    * __Binary Semaphore__
    * __Counting Semaphore__
    * __Barrier Semaphore__
    * What are mesa-style condition variables? How are they different from Hoare style?
  * __Condition Variables__
* Deadlocks and techniques for prevention
  * __No Hold and Wait__
  * __Resource Ordering__
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
  * __Interrupts__
  * __Exceptions__
* Define Interrupt Handler
* Define Exception Handler
* Distinguish between user (application) and kernel stack
* __Know how to draw processes and system calls with details regarding user and kernel stack__

#### Unit 4: Virtual Memory
* Define physical memory
* Define virtual memory and why we need it
* Understand address translation and 3 ways to do it
  * __Dynamic relocation__
  * __Segmentation__
     * __Relocation Register + Limit register__
     * __Segment table__
  * __Paging__
     * __Single Level paging__
     * __Multi-Level paging__
* Understand the role of MMU in address translation

... more to be added soon

## Extra Review
* [Past Midterm Exams](https://www.student.cs.uwaterloo.ca/~cs350/common/old-exams/)
* [Review Questions Compiled by W10 Students](https://www.student.cs.uwaterloo.ca/~cs350/common/review-questions/CS350-course-review.pdf)

## Credits

A big thank you to my Professor __Lesley Istead__ for dedicating her time to teaching this epic course and personally setting all her students up for success. I especially appreciate her initiative and effort to stream her lectures to all students this term.
