
## CPU Scheduling 

- Maximize computer processing we have
- There will be times a process is I/O Bound
	- a GPU bound game has more parts of the game relying on GPU  to process it

![[Pasted image 20250531073525.png]]

Usually, there will be parts na CPU bound or IO bound
Pag I.O bound lang software, edi no CPU. not maximizing CPU.
Developers realize pwede ka magrun ng multiple program sa same CPU. 

There will be  times the CPU will be idle

Typically a lot of operating systems usually are in the start (burst time)
![[Pasted image 20250531073818.png]]
**Image 2:** *Histogram of Burst (usually in the start)*

Pansinin, may boost clock kapag nakita yung specs ng CPU. Boost cclock kasi its possible to boost the CPU for a bit of time to process something faster. TAU Boost Window sa Intel CPU, thats what they call their burst time.

### Predicting Length of Next CPU Burst 

Estimate the length  - should be similar to the previous one
Then pick process with shortest predicted next PU burst
Can be done by using the length of precious CPU bursts, using exponential averaging.

We predict by estimation. 
The problem: mahirap magestimate sa computers kasi itself is a computation.
Some designers predict with some kind algorithm that leads to apriori information.

![[Pasted image 20250531074546.png]]

![[Pasted image 20250531074555.png]]

Baka lumabas sa exam,  explain lang:

Explanation: Mapredict next time step, predict from previous experience.

### CPU Scheduler

As much as possible, this owuld like to maximize hardware. May 4 decision points:
![[Pasted image 20250531074901.png]]

### Preemptive and Non Preemptive

Preemptive - pwede ka pigilan ng scheduler while in the middle of something
Example: inutusan ka na may gawin ka,  so bale pinigilan ka niya gawiin gusto mo
Non Preemptive: Kapag nagsimula ka ng task, di mo na pwede itigil ang task until completion

### Preemptive and Race Conditions
Better to design software than last step ka nalang magmmerge

### Dispatcher
May dispatch latency kasi: yung time na makasakay ng jeep at makaupo ka, may latency pa yun
Designers try to minimize that latency

![[Pasted image 20250531075539.png]]

![[Pasted image 20250531075546.png]]

As much as possible, the scheduler would tr to preserve processes in the same core

### Scheduling Criteria

Pero kahit gusto mo mag maximize, ayaw mo mag max CPU usage, for the sake of eco

![[Pasted image 20250531075958.png]]

Ohms Law - mas mahirap mag produce ng electricity kapag mainit ung temp

![[Pasted image 20250531080329.png]]

### First Come First Serve Scheduling

- FIFO
- Run until done
- FCFS  meant one program scheduled until done

Dati, computers are sequential. So talagang ano maunang malagay sa process, siya tatapusin muna. 

![[Pasted image 20250531081024.png]]

Throughput: the total number of processes that were done in a certain time unit 
IE., whats the throughput at 28 time unit: 2 - P1 and P2

What if may arrival time? 

### Shortest Job First - SJF

We prioritize shorter processes. We do the smaller tasks.

![[Pasted image 20250531083446.png]]

You priotizie shorter tasks. The goal is to finish a lot of things but youre putting off the big tasks  down the line. Convoy effect.

How do you find out if the job is short. Usually figure this out by virtue of number of instructions doon sa niload. 

### Shortest Remaining Time First

Preemptive version of shortest job.
Whats going to happen is youre gonna have a concept of arrival time

If the given is not ordered set, you re-order everything in terms of arrival time.

If may equal ng arrival time, you then sort it by process ID. Mas mababang PID is closer to Kernel.

### Round Robin

In the spirit of fairness, less time for completion but everybody gets to move forward.

Concept of time quantum q. everybody gets guaranteed q time units
