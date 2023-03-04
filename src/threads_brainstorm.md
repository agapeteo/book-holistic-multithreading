# Threads under the hood brainstorming

## Why multithreading

- why you reading thi book
- speed and efficiency
- Moor's law
- why clock rate is not growing that fast
- cost
- heat and power concumption

- Amdahl's law

## Thread history
3 original authors. 
from multiprogramming operating systems to multithreaded applications


## Applications, processes and threads

- what is application, 
- group of thats that help to archive some goal
- application can run one or more processes on a single or multiple computers. 

TODO langages and code
Application -> tasks -> algorithms & data structures -> code -> languages


Operating systems are about effectively running appolications on the given hardware.
Effectly could also mean
?? what is OS
That's why operating system may represent application as a runing process. 
OS limits what process can do, but in returns it gives greater flexibility and effency overall.

Process is the means by which Operating Systems runs application.
Strickly speacking, Operation System is not mandatory to run multiple processes. For example in amberdded hardware.
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





