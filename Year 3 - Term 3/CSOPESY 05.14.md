
Not a process until loaded into the main memory to be fetched by the CPU

Program in execution; progress in sequential fashion. No parallel execution of instructions of a single process. You would spawn two processes

Parts:
1. Program code - text section
2. Program counter - processor registers
3. Stack - containing temporary data
	1. Function parameters, return addresses, local variables
4. Data section containing global variables
	1. try to minimize global variables because very expensive. Even when not used, its taking up memory
5. Heap containing memory dynamically allocated during run time

Program is a passive entity stored on disk (.exe); process is active
- Program becomes process when an executable file is loaded into memory
- Scheduled task, auto run, startup or user double clicks

Execution of a program started via GUI mouse clicks, command line entry of its name, etc.

One program can be several processes.


### Process State

As a process executes, it 
![[Pasted image 20250514075344.png]]
**Image 1:** *Process state diagram from Schilbershatz*

Processes line up to be executed by the CPU in the ready queue. 
After ready queue, get scheduled by the scheduler then dispatched into running.

### Process Control Block
- Information associated with each process (also called task control block)
- Tracker of the OS of the processes
- ![[Pasted image 20250514075833.png]]
	![[Pasted image 20250514075913.png]]

![[Pasted image 20250514080104.png]]

Whats going to happen is multiple program counters for each process na. 

![[Pasted image 20250514080200.png]]
![[Pasted image 20250514080207.png]]

### Process Scheduling
Process Scheduler selects among available processes for next execution on CPU core.

![[Pasted image 20250514080447.png]]

![[Pasted image 20250514080854.png]]

![[Pasted image 20250514081302.png]]
![[Pasted image 20250514081747.png]]

![[Pasted image 20250514082150.png]]
![[Pasted image 20250514082303.png]]
![[Pasted image 20250514082516.png]]


![[Pasted image 20250514083041.png]]

![[Pasted image 20250514083622.png]]
shared memory is faster but the harder part is if multiple resources that want to write on the same memory

