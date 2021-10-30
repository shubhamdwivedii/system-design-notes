# Garbage Collection 

Determines which objects should be garbage collected by **tracing which objects are reachable by a chain of references** from certain root objects, and considering the rest as garbage and collecting them.

**Reference counting** garbage collection is where **each object has a count of the number of references to it**. 

An object's **reference count is incremented when a reference to it is created**, and decremented when a reference is destroyed. 

When the **count reaches zero**, the object's memory is reclaimed.

**Garbage Collection** only happens on **Heaps**

Function's **Stacks** are deleted automatically when function has returned. 

**Escape analysis** is a compile-time technique that can convert **heap allocations to stack allocations**, thereby **reducing the amount of garbage collection to be done**.

This analysis determines whether **an object allocated inside a function is accessible outside of it**

If a function-local allocation is found to be accessible to another function or thread, **the allocation is said to "escape"** and **cannot be done on the stack**.