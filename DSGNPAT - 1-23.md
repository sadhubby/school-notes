
# Code Smells

MCO2 would focus on code smells. Present code smells you've noticed on projects

Different types or examples of Code Smells

Syntax and Semantics
- Syntax means how do we form / construct each line of codes (form)
	- Like grammer in IRL. Kapag wala kang period sa dulo, pwedeng considered ungrammatical
- Semantics is the logic (meaning) of the line of code

Syntax --- Form --- Grammar
Semantics --- Logic --- Meaning

Code smell, like in writing a paragraph / essay
Kailangan kung ano yung contextual / relevance, yun dapat mabasa sa essay

In code smell, kahit syntax or semantic correct, when we're trying to review each line of code, nakikita natin na pwede pang iimprove. Technically may not affect the flow of the program now but it can be possible errors in the future.

We must remove them so we can practice maintainability, reliability, performance and efficiency.
Code smells are warning signs or indicators. 

--- 
## Duplicate Behavior (Duplicate Code)
	- copy the same logic or code in other places.
	- code works.. you need the  same logic elsewhere... copy and paste.
	- Repeat N times
	- Find all spots where you copy-pasted code and then make edits.
	You find yourself in a never-ending cycle of updating little spots of code all over the codebase. The routines get complex and difficult to understand. Can't be reassigned to a different project kasi... kaw lang nakakaintindi.
Solution : DRY (Don't Repeat Yourself)
- Write code in a method just once then call it where you need it.
- Use composition or inheritance to reduce deuplication
- use parameters or polymorphism to handle variations.
When you need to update, test one spot

Patterns: Utility/Helper Class, Template Method, Strategy, State, Layer Supertype.

## Long Methods and Large Classes

"Hmm, let me try to understand the method that my teammate wrote".... scroll. scroll. page-down...

Another warning sign: Class has a lot of fields.
Difficult to understand and maintain
This violated OOP since OOP is about small and specialized components.

Each method should only o one simple thing:
	No side effects
	Method name should be descriptive of that one thing, if method hard to name prolly doing too much.

A class should be specialized, cohesive unit:
	Just a few fields
	If class is difficult to name, or has a generic name, it might be doing too much or not enough.

Solutions : 
- Break up a long method into multiple smaller methods
- Break up a large class into two or more classes
- Apply SRP, Information Expert, Law of Demeter


## Primitive Obseesion, Data Clumps and Long Parameter Lists

Primitive Obsession: Sticking with built-in types of the language instead of creating one's own classes.
Sobrang daming iupdate at i-copypaste

Data Clump: Fields that are often found together

Long Parameter List: self-explanatory. method has a lot of parameters.

Solutions: 
	Cohesion  for data clump - Encapsulating data clump into meaningful classes.
	Kesa sa magupdate ka paisa-isa, isang class lang need baguhin
	For long parameter lists - move method to class, apply law of demeter 


## Divergent Change

Single class needs modification for different reasons
This breaks principle of Separation of Concerns

Soltion: Break up class to only do one concern


## Shotgun Surgery

Single change needs to update multiple classes
Cuased by lack of cohesiveness. 

Solution: Encpasulate things that change together into one class

Birds of a feather stay together.

## Feature Envy

method keeps accessing data from another class than its own

Solution: Move the method to the class where the data it uses resides
Violation of Principle of Encapsulation. Move that method to the other class nalang lmfao

Apply Information Expert / Law of Demeter.


## Conditional Complexity

Large and growing If Else and Switch logic become difficult to maintain

Violation of Open Close Principle

Solution: Polymorphism or use generic /template classes
Separate common logic from special case logc
create supertpye as placeholder for specia case logic
create subtypes   to hold logic for each special case

---

# Part 2

