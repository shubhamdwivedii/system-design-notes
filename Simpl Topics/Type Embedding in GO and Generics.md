# Type Embedding in Go 

**Go doesn't support inheritance** in the **classical** sense.

Instead, Go **encourages composition** as a way to **extend the functionality** of types.

**Composition over Inheritance** is a known principle of **OOP** and is featured in the very first chapter of the Design Patterns book.

**Embedding** is an important Go feature making composition more convenient and useful.

There are three kinds of embedding in Go:

1. **Structs in structs**
2. **Interfaces in interfaces**
3. **Interfaces in structs**


## 1. Embedding Structs in Structs:

```go 
type Base struct {
    b int
}

type Container struct { // Container is embedding Base 
    Base 
    c string 
}

func main() {
    // Instances of Container will how the field "b" as well. 
    // In go spec, "b" is called **Promoted Field** 

    co := Container{}
    co.b = 1 
    co.c = "string" 
    fmt.Printf("co -> {b: %v, c: %v}\n", co.b, co.c)

    // When using a struct literal, however, we have to initialize the embedded struct as a whole, not its fields. 
    // Promoted fields cannot be used as field names in composite literals of the struct:

    coo := Container{Base: Base{b:10}, c: "foo"}
    fmt.Printf("co -> {b: %v, c: %v}\n", co.b, co.c)

    // Note that the access co.b is a syntactic convenience 
    // we can also do it more explicitly with co.Base.b
}
```

### Methods 

Embedding structs also works well with methods. Suppose we have this method available for Base

```go 
func (base Base) Describe() string {
    return fmt.Sprintf("base %d belongs to us", base.b)
}

// We can now invoke it on instances of "Container", as if it had this method too. 

func main() {
    cc := Container{Base: Base{b:10}, c: "foo"}
    fmt.Println(cc.Describe())
}
```


# Generics In Go 

**Currently there is _NO_ support for _Generics_ in Go** 

**There is however a proposal, Generics will be added in experimantal package of Go (not std library)**

### What are Generics ?

Suppose if have a function to Add two things, And I need to add ints, strings and floats: 

I need to write three seperate functions for each. 

With generics I can write just one fuction: 

```go
func Add(a Any, b Any) Any {
    return a+b 
}
```

_That's sould be enough_