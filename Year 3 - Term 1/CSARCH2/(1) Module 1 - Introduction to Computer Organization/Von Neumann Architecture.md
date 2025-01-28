
- Store Program Architecture - program and data are stored in the main memory and NOT in the CPU.
- Instructions are **Fetched, Decoded and Executed**.
![[Pasted image 20240924132309.png]]
*The Von Neumann Architecture*

CPU communicates externally via a bus
- Bus - set of parallel wires or lines
- Three bus:
	- Address bus
	- Data bus
	- Control bus
![[Pasted image 20240924132447.png]]
*The buses of the CPU*

1. Address Bus 
	![[Pasted image 20240924172711.png]]
	*Address Bus*
	- used to select the desired memory or I/O devices
	- uni-directional (one direction only, from CPU to external).
	- x address bus, CPU could access up to  2^x
2. Data Bus 
	![[Pasted image 20240924173056.png]]
	*Data bus*
	- used to transfer data from memory to I/O devices
	- bi-directional
	- CPU has y data bus; transfer data y bit at a time

3. Control Bus
	![[Pasted image 20240924173210.png]]
	*Control Bus*
	- used to carry control signals to the memory
	- CPU has z control bus; 2^z possible control signals

![[Pasted image 20240924173439.png]]
*Try this*
**Q: Why is the range of the address that the CPU can access 0-7?**
A: ==Address bus== can access 2^x, in this case, 2^3 = 8, therefore count 8 starting from 0

**Q: Why only 8 bits transferred at a time?**
A: ==Data bus== says how many bits can be transferred at a time. amount of bits = amount of transferable. That is why 8

**Bus Clock**
- Common bus clock is used to coordinate activities in a system.
- time interval per one clock pulse is bus cycle
- Bus cycle time is inverse of bus clock rate
- There if the bus clock rate is 400 MHz, bus cycle time is:
	$$BCT = 1/BCR$$
$$BCT = 1/400,000,000 Hz$$
= 2.5 x 10^-9 seconds or 2.5 nanoseconds

**Bus capacity**
- also is called data transfer rate
- Bus capacity = data transfer unit * clock rate
- For example, a bus capacity with 64-bit data lines and a 400MHz clock rate is equal to:
	- = 64 bits * 400, 000, 000 hz
	- = 8 bytes * 400, 000, 000 hz
	- = 3, 200, 000, 000 bytes or 3.2 Gbytes / sec
	