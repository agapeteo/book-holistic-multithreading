# Atomics and memory fences

- why Peterson's solution doesn't work with my PC
- cpu cache coherance
- ordering
- perf check overview


> TODO: add atomic problems like false sharing and cache ping-pong


### volatile

`volatile` keyword has a different meaning for Java and C/C++.
C and C++ usually don't use `volatile` for memory ordering guarantees, except some rare cases like mamory-mapped IO.
volatile may help prevennting reordering with other volatile variable, but not with non-volatile variable.
So it is recommended to use locks and atomics instead. 
[See why valatile considered harmful in Linux kernel](https://www.kernel.org/doc/html/latest/process/volatile-considered-harmful.html)

Java uses `volatile` for some memory ordrering guarantees, see [JSR-133](https://download.oracle.com/otndocs/jcp/memory_model-1.0-pfd-spec-oth-JSpec/)

Rust and Go don't have `volatile` variables at all. These langauages propose using reads and writes functions.



### etc

> TODO: blog post on write bufferes https://paulcavallaro.com/blog/x86-tso-a-programmers-model-for-x86-multiprocessors/
> [whitepaper which blog is referenncing to on write buffers](https://www.cl.cam.ac.uk/~pes20/weakmemory/cacm.pdf)


[https://en.wikipedia.org/wiki/MESI_protocol](https://en.wikipedia.org/wiki/MESI_protocol)


[An Evaluation of Snoop-Based Cache Coherence Protocols, whitepaper](http://hps.ece.utexas.edu/people/suleman/class_projects/pca_report.pdf)


[! Linus Torvarld on write buffers issue note](https://yarchive.net/comp/linux/store_buffer.html)


### MESI visual interactive 

[https://www.scss.tcd.ie/Jeremy.Jones/vivio/caches/MESIHelp.htm](https://www.scss.tcd.ie/Jeremy.Jones/vivio/caches/MESIHelp.htm)

### not sure if I should include next refereces. TODO: check and decide

[An Evaluation of Snoop-Based Cache Coherence Protocols, whitepaper](http://hps.ece.utexas.edu/people/suleman/class_projects/pca_report.pdf)
