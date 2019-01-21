# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency: Two processes running interchangeably. The processor switching inbetween them.
   Parallelism: Two processes running at the same time on two separate processsor cores.
   The difference is that a concurrent process appear to tun at the same time, but is really not, while parallel processess is actually running in parallell but need separate cores.
 
 ### Why have machines become increasingly multicore in the past decade?
 > Because instructions running in parallell increase speed. Energy efficiency and is also a major reason when different cores have different energyconsumtion.
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Concurrent programs help solve situations where different tasks need to be carried out separate and concurrently.
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > Both. On one hand the concurrent program is harder to debug, on the other hand programming with threads makes the code a lot easier to read. Solving concurrent problems without concurrent programming is hard.
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > Processes are used for larger programs and have different memory spaces. Threads within a process have shared memory space and are used for smaller program tasks.
 Green threads are threads that are run in a virtual machines or runtime libraries instead of by the native operating system. Green threads emulate multithreaded environments without relying on the underlying native OS capabilities. They are managed in user space instead of kernel space which makes then able to work in environments that does not have native thread support.
 Coroutines are a generalized subroutines in non-preemptive multitasking by allowing for multiple entry points of execution and resuming at certain locations.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > `pthread_create()`: Thread
    `threading.Thread()`: Thread
    `go`: Coroutine/Goroutine/Lightweight thread
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > GIL uses mutex to lock the entire system to avoid unwanted access to memory. The negative effect of GIL is that only one thread can run at a time, making a multithreading process single threaded.
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > Create a new process (module) that run in parallell with the previous. 
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > The number of operating system threads allocated to goroutines in the program.
