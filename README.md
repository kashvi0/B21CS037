# XV Quiz (CSL 3030)

Welcome to the XV Quiz for CSL 3030 - Operating Systems!



## Instructions
- Answer the multiple-choice questions by selecting the correct option.
- For theoretical questions, provide concise and accurate explanations.
- Feel free to use this quiz for self-assessment or educational purposes.

## Multiple-Choice Questions

#### Question 1: Basics
1. What is XV6?
   - a. A programming language
   - b. A Unix-like operating system
   - c. A file system
   - d. An assembly language

#### Question 2: Architecture
2. XV6 is based on which earlier operating system?
   - a. Windows
   - b. Linux
   - c. BSD
   - d. DOS

#### Question 3: File System
3. Which file system is used in XV6?
   - a. FAT32
   - b. NTFS
   - c. ext4
   - d. simple

#### Question 4: System Calls
4. How are system calls implemented in XV6?
   - a. As functions in the C standard library
   - b. As interrupts
   - c. Through the command line
   - d. As external programs

#### Question 5: Processes
5. In XV6, what is the maximum number of processes that can run simultaneously?
   - a. 128
   - b. 256
   - c. 512
   - d. 1024

#### Question 6: Shell
6. What is the name of the shell used in XV6?
   - a. Bash
   - b. Zsh
   - c. Sh
   - d. Fish

#### Question 7: Scheduling
7. How does XV6 handle process scheduling?
   - a. Round-robin scheduling
   - b. Priority-based scheduling
   - c. First-Come-First-Serve (FCFS)
   - d. Random scheduling

#### Question 8: Memory Management
8. Which memory management technique is used in XV6?
   - a. Paging
   - b. Segmentation
   - c. Virtual Memory
   - d. None of the above

#### Question 9: Interrupts
9. How are interrupts handled in XV6?
   - a. Through polling
   - b. Using hardware interrupts
   - c. Using software interrupts
   - d. Both b and c

#### Question 10: Multithreading
10. Does XV6 support multithreading?
    - a. Yes
    - b. No

#### Bonus Question:
11. Who developed XV6?
    - a. Microsoft
    - b. Google
    - c. MIT
    - d. IBM

## Theoretical Questions

#### Question 12: Process States
12. Briefly explain the different states a process can be in within the XV6 operating system.

#### Question 13: File System Structure
13. Describe the structure of the file system in XV6. Include the key components and their roles.

#### Question 14: System Calls vs. Library Functions
14. Explain the difference between system calls and library functions in the context of XV6. Provide examples of each.

#### Question 15: Memory Paging
15. How does memory paging work in XV6? Discuss the benefits of using paging in memory management.

#### Question 16: Shell Commands
16. Name and briefly explain three essential shell commands in the XV6 operating system.

#### Question 17: Process Synchronization
17. Discuss the concept of process synchronization in XV6. Why is it essential, and what mechanisms are used to achieve it?

#### Question 18: Interrupt Handling
18. Explain the role of interrupts in the XV6 operating system. How are interrupts handled, and what is their significance in system operation?

#### Question 19: Virtual Memory
19. What is virtual memory, and how is it implemented in XV6? Discuss the advantages of using virtual memory.

#### Question 20: Boot Processlogg
20. Outline the steps involved in the boot process of XV6. What happens from the moment the computer is powered on to when the XV6 kernel is loaded into memory?


## Answers
Please write your answers here

1. b (A Unix-like operating system)
2. c (BSD)
3. d (simple)
4. b (As interrupts)
5. a (128)
6. c (Sh)
7. a (Round-robin scheduling)
8. a (Paging)
9. d (Both b and c)
10. b (No)
11. c (MIT)
12. There are 6 process states in xv6:
    a. unused: process is not allocated
    b. embroy: process is created but not running
    c. sleeping: process is waiting (might be waiting for I/O or some other priority process came)
    d. runnable: process is ready to run and waiting for scheduling
    e. running: process is currenty executing
    f. zombie: process has finished executing but it's parent has not yet reaped it
13. File structure in xv6 is hierarchical. It has directories, which can contain other directories or files, files contain data. Layers of xv6 system are:
    a. file descriptor - abstracts unix resources using file system interface
    b. pathname - provides hierarchical path names and resolves them with recursive lookup
    c. directory - implements each directory as a special inode whose content is a sequence of directory entries
    d. inode - this layer provides individual files
    e. logging - allows the higher layers to wrap updates
    f. buffer cache
    g. disk
14. System calls are a way for user programs to request services from the kernel-mode os. They are implemented as special instructions that cause a trap into the kernel, where the requested service is performed. eg: fork, exec, open Library functions are functions that are written in user-mode code and are linked into user-mode programs. They provide a higher-level interface for accessing OS. eg: printf, malloc, free
15. Paging divides physical memory into small, fixed-size pages. In xv6, each page is mapped to a page in virtual memory, which is a separate address space that is visible to each process. Advantages:
    a. reduced memory fragmentation
    b. improved address translation
    c. support for vm
16. 3 essential shell commands in the xv6 os are:
    a. ls: lists the contents of a directory
    b. cat: concatenates files and prints them to the console
    c. mkdir: creates a new directory
17. Process synchronization is the coordination of multiple processes to ensure that they do not interfere with each other. This is important because concurrent access to shared resources can lead to data races and other problems. In xv6:
    a. semaphores: semaphores are variables that can be used to control access to shared resources
    b. mutexes: mutexes are a type of semaphore that guarantees exclusive access to a shared resource
    c. locks: locks are a higher-level abstraction that can be used to protect shared data structures
18. Interrupts are signals that are sent to the processor by hardware devices or software programs. They are used to notify the processor that an event has occurred, such as a key press or a timer expiration. XV6 handles interrupts by using an interrupt vector table, which is a table of function pointers. Each interrupt type has its own function pointer, which is called when the interrupt occurs.
