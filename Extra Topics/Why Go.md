# Why Go ?

**Go is a minimalist language, and that’s (mostly) a blessing.**

**The formal Go language specification is only 50 pages, has plenty of examples, and is fairly easy to read.**

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


## Some core Go features: 

1. The **built-in frameworks for testing and profiling** are small and easy to learn, but still fully functional. 
    - There are plenty of third-party add-ons, but chances are you won’t need them.

2. It’s possible to debug and profile an optimized binary running in production through an HTTP server.

3. **Go has automatically generated documentation** with testable examples. 
    - Once again, the interface is minimal, and there is very little to learn.

4. Go is **strongly and statically typed** with **no implicit conversions**, but the syntactic overhead is still surprisingly small. 
    - This is achieved by simple type inference in assign­ments together with untyped numeric constants. 
    - **This gives Go stronger type safety than Java** (which has implicit conversions), but the code reads more like Python (which has untyped variables).

5. Programs are constructed from packages that offer clear code separation and allow efficient management of dependencies. 
    - **The package mechanism is perhaps the single most well-designed feature of the language**, and certainly one of the most overlooked.

6. **Structurally typed interfaces provide runtime polymorphism through dynamic dispatch**.

7. **Concurrency is an integral part of Go**, supported by **goroutines**, **channels** and the **select** statement.


## Go's Performance: 

First, Go is a **compiled** language.

An executable Go program typically consists of a **single standalone binary**, with no separate dynamic libraries or virtual machines, which can be **directly deployed**.

**Size and speed of generated code** will vary depending on target architecture. 

Go is **garbage collected**, protecting against memory leaks. The collection has **very low latency**. In fact, you may never notice that the GC thread is there.

The **standard libraries are typically of high quality**, with **optimized code using efficient algorithms**. As an example, **regular expressions** are very efficient in Go with running time **linear** in the size of the input. Unfortunately, this is **not true for Java and Python**.

**Build speeds**, in absolute terms, are currently fairly good.  Go is designed to make **compilation and dependency analysis easy.**

_This should be enough_