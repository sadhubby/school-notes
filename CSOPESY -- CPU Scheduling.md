
- System with single CPU core, only one process can run at a time
	- others must wat until CPU's core is free and can be rescheduled.
	- objective of multiprogramming is to have some process running at all times to maximize CPU utilization


## CPU-I/O Burst Cycle

Success of CPU scheduling depends on observerd property of processes

Process execution consists  of a cycle of CPU execution and I/O waiting time.
- Processes a,ternate between these two states
- Process execution begin with **CPU burst** then followed by **I/O Burst**


![[Pasted image 20250617234552.png]]
**Image 1:** *Alternating sequence of CPU and I/O bursts*

Th duration of CPU bursts can vary greatly from process to process and from computer to computer but they tend to have a frequency curve similar to **Image 2**
![[Pasted image 20250617234658.png]]
**Image 2:** *Histogram of CPU-burst durations*

Characterized as exponential or hyperexponential, with a large number of CPU bursts and a smull number of long CPU bursts. 
- An I/O bound program typically has many short CPU bursts. 
- A CPU-bound program might have a few long CPU bursts

## CPU Scheduler

Whenever CPU becomes **IDLE**, operating system must select one of processes in the ready queue to be executed

Selection process is carried out by CPU Scheduler which selects a process from the **processes in memory**

The records in the queues are generally process control blocks PCBs of the processes

## Preemptive and Nonpreemptive Scheduling

CPU Scheduling may take place under following four circumstances

1. When a process switches from running state to the waiting state (i.e., I/O request or an invocation of wait() for the termination of a child process)
2. When a process switches from running state to the ready state (i.e., when an interrupt occurs)
	- [[CSOPESY -- IO Hardware#Interrupts]]
3. When a process switches from waiting state to ready state (i.e., completion of I/O)
4. When a process terminates

Situations 1 and 4, there is no choice in terms of scheduling. A new process (if one exists in the ready queue) must be selected for execution. There is a choice however for situations 2 and 3

When scheduling takes place only under circumstances 1 and 4, scheduling scheme is **nonpreemptive** or **cooperative**. Other it is preemptive. 

- Under nonpreemptive scheduling, once the CPU has been allocated to a process, the process keeps the CPU until it releases it
	- so one to sawa na process
	- if something goes into the scheduler, need to finish burst time
- Preemptive scheduling on the other hand allows the cpu scheduler allows processes to cut into an ongoing process
	- can result in race conditions when data are shared among several processes.
	- consider the case of two processes that share data
		- while one process is updating the data, it is preempted so that the second process can run
		- the second process then tries to read the data, HOWEVER it is, as mentioned, in an inconsistent state

## Dispatcher

- Module that gives control of CPU's core to the process selected by CPU scheduler
	- context switching from one process to another
	- switching to user mode
	- jumping to proper location in user program to resume program

Time it takes for dispatcher to stop one process and start another is dispatch latency

![[Pasted image 20250618003010.png]]
**Image 3:** *Dispatcher*

## Scheduling Criteria

- **CPU Utilization** - keep the CPU as busy as possible
- **Throughput** - # of processes that complete their execution per time unit
	![[Pasted image 20250618003453.png]]
	- At time unit 20, P1 has not finished, so no throughput yet @ time unit 20
	- @ time unit 27, P1 and P2 have finished execution. Therefore throughput @ time unit 27 is 2
- **Turnaround Time** - amount of time to execute a particular process
	- Sum of periods spent waiting in the ready queue, executing on CPU and doing I/O
	![[Pasted image 20250618004238.png]]
	Turnaround time = Completion Time (CT) - Arrival Time (AT)
- **Waiting Time** - amount of time a process has been waiting in ready queue
	![[Pasted image 20250618004656.png]]
- **Response Time** - amount of time it takes from when a request was submitted until first response is produced
- **Fairness** - share CPU among users in equitable manner

Generally, to have the most optimized algorithm, we want to have:
- max CPU util
- max throughput
- min turnaround time
- min waiting time
- min response time

# Scheduling Algorithms


> [!NOTE] REMEMBER
> The lower Process ID is the one we will choose at times when arrival time is equal
> 	Idea behind this is that the lower process ID is closer to the kernel
> 	i.e., Pid1 is prioritized over Pid2 
> Also for priority scheduling algorithms, the lower the lower the number, i.e., priority 1 is higher in prio


## First Come First Serve (FCFS)

- FIFO
- run until done
- one program scheduled until done

![[Pasted image 20250618004947.png]]

**Convoy effect** - short process behind long process
- consider one CPU-bound and many I/O bound processes

## Shortest Job First 
- shortest-next-CPU burst
- Associate with each process the length of next CPU burst
- Use these lengths to schedule the process with shortest time 
- SJF is optimal - minimum average waiting time for a given set of processes

Later: preemptive version is shortest remaining time first

How do we determine the length of the next CPU burst?
- could ask the user
- estimate

![[Pasted image 20250618005715.png]]


- provably optimal that it gives minimum average waiting time for a given set of processes
![[Pasted image 20250618010326.png]]

![[Pasted image 20250618010337.png]]
![[Pasted image 20250618010357.png]]

## Shortest Remaining Time First

- arrival time 
- arrive at the ready queue
![[Pasted image 20250618010552.png]]
![[Pasted image 20250618011353.png]]

Since P1 happened twice, so last execution of P1 start time - first completion time of P1
10 - 1
or i guess

Final P1 start time - last time it went out of cpu scheduler

P2 start time - arrival time in ready queue  = 1-1 = 0

P3 start - arrival time in ready queue = 17-2 = 15

P4 start - arrival time = 5 - 3

## Round Robin 

- introduces another variable called **time quantum**
The ready queue is treated as a circular queue. 
- every process has a guaranteed **time quantum** number of times to be executed by the scheduler.

![[Pasted image 20250618012014.png]]


![[Pasted image 20250618012654.png]]

![[Pasted image 20250618012709.png]]![[Pasted image 20250618012740.png]]
![[Pasted image 20250618013143.png]]


## Priority Scheduling

SJF algorithm is special case of general priority scheduling

![[Pasted image 20250618013152.png]]


![[Pasted image 20250618013206.png]]

![[Pasted image 20250618013245.png]]

![[Pasted image 20250618013307.png]]
![[Pasted image 20250618013345.png]]

## Multilevel Queue Scheduling
![[Pasted image 20250618013359.png]]

![[Pasted image 20250618013443.png]]![[Pasted image 20250618013502.png]]


## Mutlilevel Feedback Queue

![[Pasted image 20250618013612.png]]

- pasa-pasahan lang

## Thread scheduling

![[Pasted image 20250618013945.png]]

![[Pasted image 20250618013951.png]]

## Multiple-Processor Scheduling

![[Pasted image 20250618014453.png]]
![[Pasted image 20250618014501.png]]
![[Pasted image 20250618014524.png]]
![[Pasted image 20250618014538.png]]
![[Pasted image 20250618014543.png]]
![[Pasted image 20250618014553.png]]
![[Pasted image 20250618014602.png]]
![[Pasted image 20250618014611.png]]

![[Pasted image 20250618014617.png]]

![[Pasted image 20250618014624.png]]

![[Pasted image 20250618014630.png]]
![[Pasted image 20250618014637.png]]

![[Pasted image 20250618014642.png]]
![[Pasted image 20250618014647.png]]