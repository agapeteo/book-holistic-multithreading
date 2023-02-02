# Introduction

The history of computing is a constant struggle for efficiency. From the first machine to the first operating systems to the multicore processors and
modern operating systems. Concurrency emerged to make resource use more efficient. It has also shaped modern operating systems and hardware along the
way.


As the hardware evolves, we can hope to solve more computationally intense problems faster. And we definitely see the impact this hope has on the
industry with the proliferation of javascript and python solutions almost everywhere: from desktop with frameworks like electron, to server side with
node.js, to even MCUs and the IoT with micropython. These solutions are far from being efficient in their resource use.

But there is a twist thanks to a thing called Moore's Law, or more precisely, to its end. Of course, we can argue about the end of Moore's Law, but
the facts are clear: it is getting harder to simply add transistors to a chip. It is also clear that the evolution of processors has shifted towards
multicore systems. So to make software more efficient and to take full advantage of the multicore CPUs, we have to employ concurrent algorithms. And
to do it effectively, we need to understand how concurrency works.

For this we have to understand relevant abstractions of computer science. But that is not it unfortunately, as we're dealing with a case of a leaky
abstraction. What we have to understand just as well is the language support for concurrency (or lack thereof, as is the case with javascript and
python), i.e. how these abstractions are implemented by our language of choice. But even that is not all. Another important aspect is what is going
on in the virtual machine, if any, and in the operating system. What is done at the level of assembly, and last but not least, what is happening in
the CPU itself.


