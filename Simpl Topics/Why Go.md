# Why Go ?

## Go is Small & Simple 

**Go is meant to be simple to learn**, **straightforward to work with**, and **easy to read by other developers**. 

**Go does not have a large feature set**, especially when compared to languages like C++, Java.

Go documentation describes Go as **“a fast, statically typed, compiled language that feels like a dynamically typed, interpreted language.”**

Even a large Go program will compile in a matter of seconds.

**Go was designed with Backend (Server-Side Programming) in mind.**

## Go vs Java 

1. **The Go library is smaller**, making sifting through it easier.

2. **Go has no error handling**. Just simple error type (Try/Catch, Exceptions/Throw are absent.) 

3. **Better and straightforward Concurrently implementation**. Run any function with *go* keyword. 

4. Go error handling is **Transparent** to readers. 

5. Golang has **panic and recover** rather than **try and catch** blocks

_Read About Panic() and Recover() in Go_

6. Go is faster than Java due to how it is compiled: **Go doesn’t rely on a virtual machine** to compile its code. **It gets compiled directly into a binary file**.


## Some Favourite Features of Go: 

1. **Concurrency**: Simply use **go** keyword. 

2. **Simplicity and Consistency**:
    - Go is a relatively simple language and was designed with a very minimalistic approach. 
    - **The standard library contains most things including a web server!**
    - Example: If the function name in a Go package starts with an **uppercase letter**, it **is exported** while all functions with lower case names are not.

3. **Go IS Object Oritented**: 
    - It may seem like Go is not object-oriented (**no classes or inheritence**)
    - Go’s replacement for classes are **structs**.
    - Go also has **interfaces** (for **polymorphism**)

4. **Interfaces are Implicit**:
    - An explicit declaration of the implementation is not required. 
    - It’s just a case of implementing the methods declared in the interface into the struct type.

5. **Super Fast Compiler**: 
    - Go’s compiler is super fast. It is easily possible to compile a large Go program within a few seconds. 
    - The fact that the language syntax is so simple means that compilation is much quicker. 
    - **The language was designed to be easily parseable without a symbol table**.