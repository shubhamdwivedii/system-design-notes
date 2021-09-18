

Thread = path of execution (diverges when async) - lightweight process with its own stack etc to maintain state 

Moving Thread to Thread is costly 

THread has fixed size (which is large) 

we can schedule multiple go routines on a thread. 

Go schedular maitains a queue of go routines for each thread. asssignes when thread is empty.

Context is copy of state of current thread so it may resume.

Not go context ctx. 

Thread state is saved to Context when it makes calls etc. 
Context switch is costly. 


CPU bound vs IO Bound processes.

Context switch is costly for CPU bound. 

Contention - Go routines waiting and competeing for CPU cycle. 

CPU Bound contension is uncessesary. 


Channels are primitives to synchronize Go routines. Channels don't need locking they implement internally. NO two Routines can read from channel at same time. 


Rate Limiter implementation go ip and userid 