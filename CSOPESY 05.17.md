
Interprocess Communication IPC

Processes within a system may be independent or cooperating.

Cooperating process can affect or be affected by other processes

Reasons for cooperating processes:
- Information sharing
	- ie., CCINFOM, connecting to database. Database is a separate process.
- Computation speedup
- Modularity
	- a program should only do one thing "specialized" so you can connect programs so that it will do that one speialized thing they do with others.
- Convenience

Cooperating process need interprocess communication
Two models: shared memory, message passing

![[Pasted image 20250517073847.png]]
**Image 1:** *shared memory vs message passing*

Nuance with shared memory is that it is kinda hard to do this if you're not used to threading in coding applications. 
The developer needs to implement message. Think of how you can't close a file when its in use with your PC.

Antoher nuance is that it really depends on compiler. 
Shared memory is very fast opposed to message passing. but its becoming negligible. Java has synchronized method which does this. 

Message passing, what they'll do is instead of passing a variable, they'll pass messages to each other. Using TCPIP stack provided by the OS, you are able to connect multiple processes to each other. The nuance of this naman is a bit overkill. The beauty of it is not need to employ a lot 

## Producer-Consumer Problem

- Paradigm for cooperating processes:
	- producer process produces information consumed by consumer process
- two variations:
	- unbounded-buffer places no practical limit on size of buffer
		- producer never waits - prof never waits for students to consume lesson
		- consumer waits if no buffer to consume
	- bounded buffer assumes that there is a fixed buffer size
		- producer must wait if all buffers are full - prof waits, the buckets full and cant take more water
		- consumer waits if there is no buffer to consume

Essentially, producer waits or doesnt wait

## IPC Shared Memory

Area of memory shared among processes

## Full Buffer

Suppose the buffer is full, it needs to have a solution for no data loss. We can do so by having an integer counter that keeps track of the number of full buffers

Set to 0

integer counter is incremented by the producer after it produces a new buffer

integer 

![[Pasted image 20250517075423.png]]
IPC Message Passing is more of throwing messages. Should be familiar with socket programming from CSNETWK

If Processes P and Q wish to communicate, they need to establish a communication link then exchange  messages via send/receive

Implementation issues:

How are links established?
Can a link be associated with more than two processes?
How many links can there be between every pair of communicating processes? 
What is the capacity of a link?
Is the size of a message that the link can accommodate fixed or variable
Is a link unidirectional bi-directional

Like wanting to talk to someone, you have to call their attention.

![[Pasted image 20250517080456.png]]

## Direct Communication

Processes must name each other explicitly:
	send (P, message) - send message process to P
	receive(Q, message) - receive from process Q
Properties:
	links are established automatically
	link is exactly one pair of communicating processes
	between each pair there exists EAXCTLY one link
	maybe bidirectional or unidirectional

## Indirect Communication
Instead of talking to me directly, you're talking to my email inbox

Messages are directed and received from mailboxes (ports) 
	processes can communicate only if they share a mailbox
	each mailbox has a UID
Properties
	link established only if processes share a common mailbox
	a link may be associated with many processes
	each pair of processes may share several communication links
	link may be uni directional or bi-directional

## Synchronization
Message passing may be either blocking or non blocking
Blocking is considered synchronous
	Blocking send -- the sender is blocked until the message is received
	- cant talk to someone else, only one
	blocking receive -- the receiver is blocked until a message is available
	- phone call. cant receive messages while talking to someone else

Non-blocking is considered asynchronous
- non blocking send - the sender sends the message and continue
- non blocking receive - the receiver receives: a valid message or null message

Blocking is associated with direct messaging
non blocking is associated with indirect communication

## Buffering

Queue of messages attached to the link.
Implemented in one of three ways
1. Zero capacity - no messages are queued on a link
	1. Sender must wait for receiver (rendezvous)
2. Bounded capacity - finite length of n messages
	1. sender must wait if link full
3. Unbounded capacity - infinite length
	1. sender never waits

![[Pasted image 20250517081709.png]]

![[Pasted image 20250517081714.png]]

## Pipes

Acts as conduit allowing two processes to communicate

Ordinary pipes - cannot be accessed from outside the process that created it. Typically a parent process creates a pipe and uses it to communicate with child process that it created

Named pipes - can be accessed without a parent-child relationship

## Ordinary Pipes
allow communication in standard producer-consumer style

producer writes to one end (write end of the pipe)
consumer reads from the other end (read end of the pipe)

ordinary pipes are therefor unidirectional

require parent child relationship between communicating processes

windows calls these anonymous pipes

## Named Pipes
Named pipes are more powerful than ordinary pipes

Communication is bidrectional

no parent child relationship is necessary between the communicationg processes

 several processes
both UNIX and windows use this 

## Client Server Systems
1. Socket programming
2. Calls


## Socket 
- defined as endpoint for communication 
- Concatenation of IP address and port - a number included at start of message packet to differentiate network services on a host

3 types of socket
- connection oriented TCP
- connectionless UDP
- multicast Socket class

![[Pasted image 20250517082558.png]]


