# Threads under the hood brainstorming

## Why multithreading

- why are you reading this book?

History of computing through the lens of efficiency. From early operation systems to present day. You can use threads to use CPU efficiently.
We can either create efficient software or keep wasting money on suboptimal algorithms. The choice is yours. You can safe the world from the farting cows and AOC.
When we talk about history we talk about hardware, OS, and programming languages, how they evolved together and influenced one another.

TODO: insert a graph of energy use by language.

## Applications, processes and threads

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

## Why use threads?
- speed and efficiency
- Moore's law
- why clock rate is not growing that fast
- cost
- heat and power consumption

- Amdahl's law

## Thread history
3 original authors. 
from multiprogramming operating systems to multithreaded applications



Operating systems are about effectively running applications on the given hardware.
Effectively could also mean
?? what is OS
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


-- responsibility OS

safety
resources 
memory

memory types
code - data

stack
memory segments

Each thread own stack, registers, but everyhting else is shared

compiled application format for OS - ELF, ...

preemtive, cooperative

OS CPU allocation 


--- hardware --

cpu structure

ISA & mictoarchitecture separation

slow memory


code reordering

------

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

----


--- THREAD anaylogy probably with baristas





