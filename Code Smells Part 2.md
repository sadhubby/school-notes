
## Parallel Inheritance Heirarchy

- Every time you add a class to one package, you have to add a class to another package

Customer -> CustomerService
Order -> OrderService
Product ->ProductService

Solution: Cohesion - Move shared functionality from one hierarchy to the other then collapse.
So like its under a Class Service para hindi isa isa and all you have to add is under class Service.

Pattern: Rich Domain Model

## Lazy Class, Middle Man and Dead Code

Lazy Class: Doesnt justify existence cuz minimal to no work

Middle Man: Delegates to another class but doesn't add its own value. Tagatawag lang / Tagacall lang

Dead Code: Code no longer used

Solutions: Any code that exists takes maintenance cost; Eliminate code that doesn't justify its existence

Lazy Class: Inline its behavior into other classes

Middle Man: Combine the Middle Man with thhe class to which it delegates

Dead Code: Delete it

## Alternative Classes with Diff. Interfaces

Classes that are similar but are not substitutable since do not share supertype

Solution: Have classes share a Common interfaces/supertype

Polymorphism - so agnostic implementation

Patterns: Strategy, State
## Data Class or Anemic Domain Model

Class that only contains data and not behavior

Class is there but no functionality. Puro data lang siya

Solution: Implement RIch Domain Model or Information Expert.
Remove unneeded getters and setters to preserve encapsulation.


## Refused Bequest

When subclass inherits members it doesnt need
Dangerous if unneeded members are part of the interface

Solution: Replace inheritance with composition. Include only the behaviors they need

## Speculative Generality

Advanced magissip
When code is written ot be more flexible than present requirements

Usually in anticipation of future requirements.

Can lead to bloated hard to maintain code

Solution:
YAGNI - You aint good need it
DTSTTCPW - do the simplest thing that could possibly work

Focus on the more certain requirements - those in the current Sprint.

Code is simpler, more readable, less likely to be buggy, gets done on-time

## God Class / God Method

Much of the code is concentrated in one class or many other classes or methods. 

SRP
Information Expert
Law of Demeter

Break up classes to improve modularity and readability.

## Temporary Field

Class or instance fields that are temporarily set for method operations Dont describe the state of the object

Dangerous in multithreaded environment

Might be difficult in the future to know what its for

Solution: make the field a local variable.

Prevents unintended side effects

## Message Chains or Train Wrecks

Reaching into object's attrivutes to call the attributes methods

May utos sakin, iuutos ko saa iba tas iuutos nya sa iba

Solution: Apply Information Expert / Law of Demeter

Dont get the fields. create a method that does the work and just get the results
easier to read and maintain 

## How comments

If you need a comment to understand how some code works, then the code is not readable

"Why" Comments are better. Javadoc comments that state the contract overridden methods need to keep are also good.

Replace magic numbers with explaining variables

instead of >= 6
can be MAX_SOMETHING_NAME = 6.

Variable name that serves its meaning

if a variable or method sitll needs a how comment, rename the variable or method
	



