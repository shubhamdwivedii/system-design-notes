# SOLID Principles 

**Robert Martin** published his book, **_Agile Software Development_**, Principles, Patterns, and Practices. In it he described five principles of reusable software design, which he called the SOLID principles:

1. **Single Responsibility Principle**
2. **Open / Closed Principle**
3. **Liskov Substitution Principle**
4. **Interface Segregation Principle**
5. **Dependency Inversion Principle**


## Single Responsibility Priciple (S): 

_**A class should have one, and only one, reason to change.**_

Less **Coupling & Cohesion**


## Open Closed Principle (O): 

_**Software entities should be open for extension, but closed for modification.**_

Try using **Dependency Injection**


## Liskov Substitution Principle (L):

**Liskov substitution principle states, roughly, that two types are substitutable if they exhibit behaviour such that the caller is unable to tell the difference.**

Go does not have classes, or inheritance, so substitution cannot be implemented in terms of an abstract class hierarchy.

Try taking **Interfaces** as arguments instead of solid **structs**. 


## Interface Segregation Principle (I):

**Clients should not be forced to depend on methods they do not use.** 

Again try taking **Custon Interfaces** with **only methods that are needed** in arguments. 


## Dependency Inversion Principle (D):

**High-level modules should not depend on low-level modules. Both should depend on abstractions.**

**Abstractions should not depend on details. Details should depend on abstractions**

In Go, your **import graph must be acyclic**. 

A failure to respect this acyclic requirement is grounds for a **compilation failure**, but more gravely represents a serious error in design.