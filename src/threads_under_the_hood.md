# Threads under the hood

- sort file without joining. note on main thread
- sort file with joining and mutex and going deep:
  - language level
  - compiler level
  - assembly level
  - operating system level
  - cpu level
  - same example in Assembly
  - summary

> TODO: add note about thread cancellation

from The Linux programming interface:

> The execution of a thread terminates in one of the following ways:

• The thread’s start function performs a return specifying a return value for the thread.

• The thread calls pthread_exit() (described below).

• The thread is canceled using pthread_cancel() (described in Section 32.1).

• Any of the threads calls exit(), or the main thread performs a return (in the main() function), which causes all threads in the process to terminate immediately.

include <pthread.h>

void pthread_exit(void *retval);

Calling pthread_exit() is equivalent to performing a return in the thread’s start function, with the difference that pthread_exit() can be called from any function that has been called by the thread’s start function.

The retval argument specifies the return value for the thread. The value pointed to by retval should not be located on the thread’s stack, since the contents of that stack become undefined on thread termination. (For example, that region of the process’s virtual memory might be immediately reused by the stack for a new thread.) The same statement applies to the value given to a return statement in the thread’s start function.

The pthread_exit() function terminates the calling thread, and specifies a return value that can be obtained in another thread by calling pthread_join().

> If the main thread calls pthread_exit() instead of calling exit()
> or performing a return, then the other threads continue to execute.

> TODO: add notice about hazard pointers and similar?

