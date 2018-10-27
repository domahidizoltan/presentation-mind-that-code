# Clean Code


### What bad code means to your Project

The desirability of a new feature depends on it's value and the effort to implement it. This effort is the sum of 
efforts taken during understanding, changing, testing, deploying and maintaining the feature. This effort could degrade 
or eliminate the desirability of a feature when they are too expensive. 

As the codebase grows it's getting easier to create a mess and it's getting harder to understand and change anything. 
This growing mess reduces developer productivity and makes deadlines harder to keep. It is also increasing the probability 
of bugs and could lead to performance degradation on a long term. Many times management add more staff to 
the project, what could also slow down the development by increasing the communication effort.

Technical debt <sup>(1)</sup> means a trade-off what often needs to be made to meet the schedules. These technical debts 
must be paid back sooner or later, but the effort to eliminate them grows as time goes by (Le Blanc's law: **Later = Never**).


### What good code means to your Project

You can increase the productive working time by decreasing the time of reading and understanding source code 
(read less = write more). 

Smart developers can write code what only they can understand, causing more trouble. Everyone will ask them about the 
code, especially new team members and juniors. This is a waste of time, especially for the "smart" author. 
It is much effective and professional to write a code what is easy to understand and reveals intent. This will also reduce 
the chance to create bugs by not understanding the details and it is helping the debugging process in case of any problems. 

Just think about it. How fast can you read this sentence:
> tHisisanOrmalseNtencewitNorMalwordstAtEverybOdycAnunderStaNd.

... and how fast can you read this?
> This is a normal sentence with normal words that everybody can understand.

They are the same with different formatting. In the first example it is even harder to spot mistakes 
(wit<strike>h</strike>NorMal, wordst<strike>h</strike>At)

"Clean code always looks like it was written by someone who cares." (Michael Feathers)


### Clean Code principles

Clean Code is a set of principles and design patterns trying to help you write simple and easily understandable code. 

* **Meaningful names**: 
  - reveal your intent of usage (don't comment names)
  - avoid disinformation
  - add meaningful context
  - use as part of speech (read as sentence)
  - pronounceable names
  - avoid encodings and abbreviations
  - avoid mental mapping (short names like i, j, k in iterations)
  - use factory methods when constructors are overloaded
  - beware of using names which vary in small ways
  - scope rule: *Variables with short scopes can have short names, but with long scopes can have long names. 
  Functions and classes with long scopes can have short names, but with short scopes can have long names.* (public method 
  names should be short, but private method names can be long, they can be considered as comments)

* **Functions**:
  - should be small (4-5 lines; should do 1 thing only and use single level of abstraction; transform large functions
  to classes)
  - follow the Step Down rule: read code as a top-down narrative, using single level of abstraction (public methods define
  high-level abstraction, private methods define low-level abstractions)
  - use descriptive names (Wards's principle: "You know you are working on clean code when each routine turns out to be 
  pretty much what you expected.")
  - minimize arguments (arguments makes confusion, use 3-4 at most, and avoid booleans)
  - avoid Switch statements (hard to keep it small and could be dependency magnet; use design patterns instead like 
  Abstract Factory or Strategy Pattern)
  - avoid side effect (use functional programming instead)
  - use Command Query Separation (functions should do something or answer something)
  - prefer (runtime) exceptions instead of returning error codes
  - extract try-catch blocks (it obscures logic)
  - never return null
  - avoid early exiting loops (makes harder to understand the loop)
  - DRY: Don't Repeat Yourself (duplication is the root of all evil in software)
  - KISS: Keep It Simple, Stupid!

* **Comments**:
  - "Don't comment bad code - rewrite it!" (comments are failures of expressing yourself with code; inaccurate comments 
  are misleading and they are even worse than no comments)
  - use proper function and variable names instead of comments
  - remove commented-out code (use version control)
  - no position markers, no html comments
  - no TODO comments
  - good comments are:
    - legal comments
    - informative comments (i.e. explaining regexp pattern)
    - clarification, warning of consequences (i.e. unexpected behaviour of a tool or library, expensive computation)
    - API documentation

* **Classes**:
  - should be small (150-200 lines; small files are easier to understand)
  - should have single responsibility (should have one reason to change)
  - high cohesion (methods and variables of a class hang together as a logical whole)
  - low coupling (it is well isolated from the system and it's changes; use Dependency Inversion Principle to depend on 
  abstraction)
  - Law of Demeter: don't talk to strangers (a module should not know about the innards of the objects it manipulates)
  - favor composition over inheritance
  - YAGNI: You Ain't Gonna Need It (don't bring unused complexity until you need it)
  - beware of optimizations (they are always expensive and makes code harder to read)
  - make is SOLID:
    - **S**ingle responsibility principle
    - **O**pen-closed principle: a module should be opened for extension but closed for modification
    - **L**iskov substitution principle: objects of a type should be replaceable of their subtypes without altering the 
    correctness of the program
    - **I**nterface segregation principle: depend on many fine-grained interfaces
    - **D**ependency inversion principle: details should depend on abstraction and not the other way around

* **Unit tests**:
  - use domain-specific language
  - single concept per test
  - use TDD for better code design
  - make it FIRST:
    - **F**ast: you should be able to run them after every change, so all of them must run in less than a second
    - **I**ndependent: should run in any order and should not depend on other tests
    - **R**epeatable: should be always running on every environment
    - **S**elf-validating: should indicate clear success or failure without the need of further investigation
    - **T**imely: should be written before production code to help the code design

<br/>
<br/>

Forming habits is hard. Replacing bad habits are the hardest. Clean Code and TDD are your friends at work, so make them 
a habit, not a choice.

<br/>

### Recommended readings

- 1 - [The technical debt quadrant](https://martinfowler.com/bliki/TechnicalDebtQuadrant.html)  
- [Robert C. Martin - Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [Max Kanat-Alexander - Code Simplicity: The Fundamentals of Software](https://www.amazon.com/Code-Simplicity-Fundamentals-Max-Kanat-Alexander-ebook/dp/B007NZU848)
- [Clean Code Cheat Sheet](https://www.planetgeek.ch/wp-content/uploads/2014/11/Clean-Code-V2.4.pdf)
- [The Essence of "Clean Code"](http://www.inf.fu-berlin.de/inst/ag-se/teaching/K-CCD-2014/Clean-Code-summary.pdf)
- [Refactoring Guru](https://refactoring.guru/)
- [clean-code-developer.hu](http://www.clean-code-developer.hu/)
