# Threads under the hood brainstorming

## Why multithreading

- why are you reading this book?

First we need to understand how to solve the problem: which tools are available, which ones are best suited for it, restrictions, infrastructure.

- fill in knowledge gap
- write apps more perfomant and efficient.
- etc

Fortunately, you're not alone or first....


Then new layers appeared, like languages, OS.

But still need to solve stalls. New parallelism, but new problems like deadlocks etc.
Languages chose different approaches: some limit access to multithreading facilities while others avoid altogether.
Concurrent languages that are not parallel (Python, JS) vs concurrent languages that are parallel.
So some languages avoid deadlocks by completely avoiding parallel execution. Python and friends lack granular access control to shared state.

Even thread as a term does not describe the nature of the abstraction. Other terminology is awkward to say the least (like lock-free algorithms that are not lock free).
Parallel, concurrent, async, coroutines, and non-blocking - people don't really understand the terms. Most regard them as synonyms.
Hard to imagine what a coroutine means. What the heck is continuation? We will try to disentangle all of these for you using as simple terms as possible (illustrate with figures).
Stackless coroutines - why are they stackless. And other confusing terms.

We will use the Pareto principle - i.e. we will explain the things that are used the most in greater detail. 

Formal multithreading by Dijkstra and gang.

Same hardware improvement, but hardware limits. + Moore's law

Complexity dilema with 2 ways: not efficient, or learn multithreading.

We prefer second option.

Electricity analogy: it can kill you if you're careless or it can do a lot of wonderful things if you know how to use it.

So what is thread? Abstraction and potentially leaky abstraction.

Review of abstraction level in theory and then in practice.

History of computing through the lens of efficiency. From early operation systems to present day. You can use threads to use CPU efficiently.
We can either create efficient software or keep wasting money on suboptimal algorithms. The choice is yours. You can safe the world from the farting cows and AOC.
When we talk about history we talk about hardware, OS, and programming languages, how they evolved together and influenced one another.

TODO: insert a graph of energy use by language.

## Applications, languages, processes, and threads

- what is application, 
- group of tasks that help to archive some goal
- application can run one or more processes on a single or multiple computers. 

TODO languages and code
Application -> tasks -> algorithms & data structures -> code -> languages

Applications consist of structure or sequence of tasks. Tasks are solved by applying algorithms to data structures.
Algorithms and data structures are represented with programming languages, which translate human concepts into binary machine code of specific hardware.
As you have probably noticed, we've described a chain of abstractions. Let's make a brief detour and discuss what is an abstraction.
Abstraction is notion that separates something generic (general) from specific. Why would we need that?
It helps us recognize and apply patterns to a group of notions while ignoring unrelated details. When some details become relevant, an abstraction becomes leaky.
We have noticed that threads are often described with leaky abstractions. They can work at some level of analysis, but inevitably break down...

So to understand threads we need holistic approach. What do we mean by that? An approach that weaves together a problem itself, architecture,
data structures and algorithms, a language, a compiler, an operating system, system calls, assembly language, and even specifics of hardware in a comprehensive whole picture.

### A problem
Importance of separating of what to do from how to do it. Don't mix it up. Resist is someone is trying to tell you how to do something instead of telling what needs to be done.
In other words, you should always understand what you are trying to achieve before you start thinking about the particular ways to achieve it.
Requirements: business, functional, non-functional (SLA, throughput, latency, real-time, performance).


## Why use threads?
- speed and efficiency
- Moore's law
- why clock rate is not growing that fast
- cost
- heat and power consumption

### Architecture
We need to understand high-level components of the system and their interactions without focusing on specifics of implementation. This is when we start considering
some components as separate parallel nodes, processes, or threads. 

### Algorithms and Data Structures
This is the layer where specifics of multithreading starts to emerge.

### Languages
Every language has a specific niche, and although they may overlap, some languages are better suited to your problem than others.
You also have to take into account the developer's background, organizational restrictions, and existing standards and infrastructure.
We are going to be focusing mostly on parallel languages like Java, C++, Rust, and Go, rather than just concurrent languages like JS, Python.
Parallel vs concurrent - concurrency is a property of code, while parallelism is a property of an execution model.
The authors maintain that in most cases readability tops speed of writing code (we talk about verbosity of languages in some sense - Python is less verbose than Java,
but Java is more readable).

### Compiler
Compilers translate the human-readable code of the program into machine code in the most efficient way because it generates code optimized for specific hardware.
It can also reorder instructions to optimize performance, which has its implications for multithreading.

### Operating system

Operating systems are about effectively running applications on the given hardware.

Most important part of the OS is its kernel, which manages access to the shared hardware. System calls - what vs how we do it. If we have system calls,
we don't care about the particular implementation of the OS (where stable system calls are available).
The concept of thread only exists within the OS. Threads are made possible by a scheduler and virtual memory. If you don't have an OS, you can still have threads, but you would
have to at least implement your own scheduler and that's half way to OS itself.

- todo: why operating systems uses concept of process (explain + ralation to scheduler)
- todo: add more on process specific information (pid, parent pid, page table, environment, virtual memory, 'nice' priority, user, capabilities, current dir etc) 
- todo: addd more on thread specific informaion

Each thread has its own stack. How a thread differs from a process. Preemptive vs cooperative scheduling. Mapping software to hardware threads.
TODO: Process memory segments. Thread vs process (program counter, stack(s) (see below), registers etc)

That's why operating system may represent application as a runing process. 
OS limits what process can do, but in returns it gives greater flexibility and effency overall.

Process is the means by which Operating Systems runs application.
Stricktly speaking, Operation System is not mandatory to run multiple processes. For example in amberdded hardware.
But you still need to schedule processes somehow, so you need at least a scheduler to manage multiple processes.

Creating a process is complex task that includes:

- finding and allocting memory
- etc.. TODO
- TODO

it's not even an exhastive list

But there is another OS abtraction that can significantly simplify the way we can execute code on a given cpu - 
THREADS
T
THREADS ARE

### Assembly language

Human readable version of machine code. You rarely need to write it but you have to know how to read it because it's a great way to understand what the CPU is actually doing.

### CPU

ISA vs hardware architecture. Clock rate. Accessing memory takes centuries, so we need caches. CPUs are optimized for single-threaded execution.
Branch prediction, speculation, pipelining.

there are groups of instructions: arithmetic (add, multiply etc), comarisons (>, <, =), byte shifts, logical (and, or), store, load, branch (usually involves FLAG registers), 
jumps (goto), sync (atomic), system interrupts (syscall)

each instruction takes next clock cycles: fetch, decode, execute, write,
can we fetch next instruction while executing decode or other instruction? yes pipelining

but pipelining still can has a hazard and stalls,
so we can use branch prediction logic and also speculative executions

store and load are very slow, so we use caches.
even we don't have caches we still may have race conditions with CPU (f.e DMA call)

more on caches in Atomics.

Process build-in parallelism: pilpelineing ILP (logic parallelism) & SIMD (data parallelism)

what we can see is that CPU is very optimised for single thread execution, 

clock rate increasing non-liner energy use and heat (which is critical for mobile devises)



## let's check what we discussed in practice




example

Java thread withot join, with join
bytecote -> JVM -> clib, pthread -> ELF 

C example with phread
C++ woth thread -> pthread, glibc or musl, nptl, ....

Go and friends

RUST

strace CLONE, FUTEX

?? pthread cancellation 

assembly snippet


---

Your program is thread-safe when it has no shared state, but in this case it is unlikely to use hardware in the most efficient way.

---

--- THREAD anaylogy probably with baristas





