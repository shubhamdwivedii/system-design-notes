# Defer, Panic, and Recover 


### Defer 

A **defer statement** pushes a function call onto a list. 

The list of saved calls is executed **after the surrounding function returns**. 

Defer is commonly used to simplify functions that perform **various clean-up actions**.

**A deferred function’s arguments are evaluated when the defer statement is evaluated.**

**Deferred function calls are executed in Last In First Out order after the surrounding function returns.**

**Deferred functions may read and assign to the returning function’s named return values.**

In this example, a deferred function increments the return value i after the surrounding function returns. Thus, this function returns 2:

```go
func c() (i int) {
    defer func() { i++ }()
    return 1
}
```

### Panic 

**Panic** is a built-in function that **stops the ordinary flow of control** and begins **panicking**.

When the function F calls panic, **execution of F stops**, any **deferred functions in F are executed normally**, and then **F returns to its caller**.

**To the caller, F then behaves like a call to panic.**

**The process continues up the stack until all functions in the current goroutine have returned**, at which point **the program crashes**.

**Panics can be initiated by invoking panic directly**. They can **also be caused by runtime errors**, such as **out-of-bounds array accesses**.


### Recover 

**Recover** is a built-in function that **regains control of a panicking goroutine**.

**Recover is only useful inside deferred functions.**

During normal execution, **a call to recover will return nil** and have **no other effect**. 

If the current goroutine is **panicking**, a call to **recover will capture the value given to panic and resume normal execution**.

```go 
package main 

import "fmt" 

func main() {
    f() 
    fmt.Println("Returned normally from f.")
}

func f() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered in f", r)
        }
    }() 

    fmt.Println("Calling g.")
    g(0)
    fmt.Println("Returned normally from g.")
}

func g(i int) {
    if i > 3 {
        fmt.Println("Panicking!")
        panic(fmt.Sprintf("%v", i))
    }
    defer fmt.Println("Defer in g", i)
    fmt.Println("Printing in g", i)
    g(i + 1)
}
```