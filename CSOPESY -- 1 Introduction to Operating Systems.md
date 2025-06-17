

**What is an operating system?**
- Program, intermediary between user and computer hardware

Goals:
1. Execute user programs and make solver problems easier
2. Make computer system convenient
3. Use computer hardware in an efficient manner
	1. Manage power consumption or battery life
	2. Try to manage throttling ng CPU, for example, Parking the cores if di kailangan. Bale parang free loaders sila pero ok lang for saving power and conserving energy. Trabaho iyan ng operating system


## Computer Structure

- Hardware
	- CPU, Memory, I/O, Storage 
		- Essentially, lahat ng na sa task manager mo
- Operating System
	- Controls and coordinates use of hardware
- Application Programs
	- define ways which system resources are used to solve the problem
	- word processors, brower, compilers, video games
- Users
	- Literally the ones using the OS
	- OS allows multi-user environment

![[Pasted image 20250615203840.png]]
**Image 1:** *Computer Structure with users*

![[Pasted image 20250615203932.png]]
**Image 2:** *How hardware and applications communicate using OS*

**Why Study OS?**
- all code runs on top of an operating system
- studying OS gains additional knowledge that can lead to proper, efficient, effective and secure programming

## Operating System Definition

**1** Operating System is a resource allocator
- Siya ang nagb-budget ng resources 
	- Think of your weekly allowance
- Decides between conflicting requests for efficient and fair use
- Manage resources such that some process can run

**2** Operating System is a Control program
- Controls execution of programs to prevent errors
- Worst case scenario, BOSD if OS is being improperly used
	- 

**3** OS is the one program running at all times on the computer (i.e., the kernel)
- kernel is core of any modern operating system
	- cpu scheduling, memory management
- System programs - software not part of kernel but associated with OS
	- Windows Explorer is part of OS. If dinelete siya sa taskbar, mawawala yung UI. Its not a critical part of the OS but not really needed (i.e., server only distribution)
	- Task Manager, built into the OS, but not really necessary to running the OS.
- Middleware - set of software frameworks that provide additional devices
	- ALUs, Carry Look-ahead 
- Application programs
	- Anything not necessary for the usage of the operating system

## Process Management

- Create, delete user processes (i.e., Offing explorer)
- Scheduling processes and threads in CPUs
	- ![[Pasted image 20250615205957.png]]
		**Image 3:** *Linux task manager using bpytop (I use arch btw)*
- Suspending and resuming processes
	- Example, if naggenshin ka and naoff yung screen mo sa phone, youll get back to the splash screen
- Providing mechanisms for process synchronization
- Providing mechanisms for process communication

## Memory Management

- Keep track which parts of memory are currently being used
- allocating and deallocating memory space as needed
- deciding which memory needs to be into and out of memory 

![[Pasted image 20250615210914.png]]
 **Image 4:** *Memory usage (in bpytop, using arch btw)*

- General purpose computers run most programs from rewritable memory, called main memory (RAM)
	- Main memory - commonly implemented in a semiconductor tech called dynamic random-access memory (DRAM)
- We follow Von Neumann Architecture where the CPU cannot process something that is not in memory.
	- fetch instruction from memory, store instruction in instruction register. instruction is then decoded and may cause operands to be fetched from memory and stored in some internal register
	- After instruction of operands is executed, result may be stored back into memory


> [!NOTE] Storage Definitions and Notation Refresher
> Basic unit is **bit** - 0 or 1
> **Byte** is 8 bits
> **Word** is one or more bytes
> **Kilobyte** is $1024$
> **Megabyte** is $1024^2$
> **Gigabyte** is $1024^3$
> **Terabyte** is $1024^4$


Ideally, we want the programs and data to reside in main memory permanently. This arrangement usually is not possible on most systems for two reasons:
1. Main memory is usually too small to store all needed programs and data
permanently.
2. Main memory, as mentioned, is volatile—it loses its contents when power
is turned off or otherwise lost.

Most computers provide secondary storage as extension of main memory. Most common are Hard Disk Drives - HDDs and Non Volatile Memory - NVM's devices
## File System Management

- Creating and deleting files
- Creating and deleting directories to organize files
- Supporting primitives for manipulating files and directories
- Mapping files onto mass storage
- Backing up files on stable storage

## Cache Management

- Temporary storage that is fast (i.e., registers, cache, memory disks)
- OS manages hierarchy of storage
![[Pasted image 20250615212411.png]]
- OS are actually responsible for NCQ (native command queueing), kung paano umiikot yung disk, si OS rin nagscschedule niyun. 
	- Minsan depende rin sa laki ng drive

## IO System Management

- Input devices also handled by OS
- Component that includes buffering, caching and spooling
- Modern general purpose computer consists of device controllers connected through a common bus
	- access between components and shared memory
	- depending on controller, a lot of devices can be connected
		- system USB port can connect to USB hub, several devices can connect to that
		- maintains local buffer storage and set of special registers
- General device-driver interface
- Drivers for specific hardware devices
	- N-Key Rollover from gaming keyboards
	- Back then KBs cant handle simultaneous input na apat, pero what if youre an esports player with high APM? The kbs cant keep up
	- What they did was KBs got buffer circuits added to them. Keyboard manufacturers added custom buffers but now they had to install custom drivers.
	- Drivers expands capabilities of the operating system
![[Pasted image 20250615225419.png]]

## OS Services

- OS provides execution environment for programs by providing services available
- Available services available varies depending on operating system and hardware

![[Pasted image 20250615213620.png]]
**Image 5:** *All the systems calls are provided by the OS*

## System Calls

- API ng OS to the world
- Parang assembly programming language but higher level

Kapag cinompile lahat ng system calls, you create a compiler

An example of a system call is doing the command cp in.txt out.txt
cp in linux is copying a file, so this copies in.txt content into out.txt\
So opening the in.txt file is a system call, accessing out.txt file also a system call. Error handling is a system call

![[Pasted image 20250616115713.png]]

API - application programming interface - set of functions that are available to an application programmer, including the parameters that are passed to each function and the return values the programmer can expect

Here is how API calls are handled by the OS
![[Pasted image 20250616115908.png]]


System call interface serves as alink to system call made available to OS and Run Time Environment. 

- This is why applications are not cross-compatible across OS'. Iba-iba kasi system calls ng OS

## Portability

- Due to variances of system calls from one OS to another
- Portable applications are still possible using following techniques
	- Interpreted programming language (python, ruby, nodejs), interpreter reads each line of program and executes equivalent instructions native to OS
		- Yes may overhead and theoretically a bit slower pero computers are now faster
	- PL includes its own full Runtime Environment (Java) - RTE abstracts system calls from program
	- Standardized use of API related to compilation of binaries (POSIX, UNIX) 

## OS Structures - Monolithic

- All functionality is in a single static binary  file
- I.e., Linux
- Tightly Coupled
- If something goes wrong in any component, then it will crash

## OS Structures - Layered

- Modular components - layered where lowest layer is the hardware and highest layer is UI
- Loosely coupled
- Changes can be modular

I.E., Vanguard from Riot Games is said to be Kernel-layer anticheat
Kernel layer can see outward but no one can see in ward

Another example, shutting down Windows Explorer. It can be closed without bringing the OS with it kasi its in the outer ring

![[Pasted image 20250615214745.png]]
**Image 6:** *Layering*

## Microkernels

- Carnegie Mellon University developed an OS caled Mach that modularized kernel using micro-kernela approach
- OS resistant to failure

New services are added to the user space without modification

- If service fails, OS is left untouched
- Darwin,  used by macOS and iOS

![[Pasted image 20250615215011.png]]
**Image 7:** *macOS and iOS structure*

Images below: Layering of macOS and iOS
![[Pasted image 20250615215113.png]]
![[Pasted image 20250615215103.png]]


## Android Structure

![[Pasted image 20250615215143.png]]
![[Pasted image 20250615215151.png]]

## Virtual Machines

- Layered approach
- Operating system on top of another operating system
- May overhead but minimized because modern processors would have this Virtualization instruction set.

![[Pasted image 20250615215349.png]]
**Image 8:** *Virtualization instruction set from Intel*

Virtualization instruction set allows us to run virtual environments as if they're native, removing that layering.

