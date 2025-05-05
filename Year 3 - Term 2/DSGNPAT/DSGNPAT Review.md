

1. Class should have only one reason to change 
	A: Single responsibility principle

2. which pattern allows incomptabily interfaces to work together 
	A: adapter pattern

3. consequence of execessive use of conditionals 
	A: increased complexity 

4. pattern for creating complex objects step by step
	A: builder pattern

5. what does the term god class refer to 
	A: a class with too many responsibilities

6. pattern that encapsulates interchangeable algorithms 
	A: strategy pattern

7. shotgun surgery indicate in code design 
	A: a single change requires multiple edits

8. which principle is volated when a class handles unrelated functionalities
	A: single responsibility principle

9. what is the purpose of null object pattern 
	A: to replace null references with a default object

10. which pattern minimizes memory usage by sharing common parts of objects
	A: flyweight pattern 

11. what doe sfeature envy refer to 
	A: method that interacts execessively with another class' data

12. which pattern groups multiple db ops into a single transaction 
	A: unit of work pattern 

13. what is the main goal of the repository pattern
	A: separate business logic from data access 

14. what does divergent change indicate 
	A: class modified for unrelated reasons


Singleton Design pattern
1. Problems that it solves
	- unnecessary multilple instances.
	- shared resource like a database
	- unsafe global variable use
	- any code can modify the global variable causing unexpected pattern

- creational design pattern, calls the original instances
- one single safe access point of shared instances

no need to use globla variables

think of a car key as a singleton instances. instead of multiple keys, only one key to open a car. multiple keys pose security risk

most often used for shared resources like caches, db, config settings. also for coordinating system wide application and sessions

Frameworks: 
1. Redux Overview
	state amangement library that helps you manage and centralize application state in a predictable way. 
	uses pure functions or reducers to update state consistentyly
	unidrectional data flow, state ujpdates follow a strict flow:  action > reducer > store  > UI 

2. Express JS
	used for buildings web servers and apis - handles http requests efficiently
	ok youre web app developer, you should know this 

why it can be antipattern

sometimes singleton makes things more complex, often when misused and multiple instances are actually required. in multithreaded environments, the singleton pattern could result in concurrency issues as well

![[Pasted image 20250403081447.png]]

