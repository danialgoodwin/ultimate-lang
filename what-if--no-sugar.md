
What if there no syntactic sugar in this programming language?

The goal of this project is to see what a programming language could look like with no syntactic sugar (SS). Could it be simple if designed well?
- Probably Lisp. But, what if it isn't all parentheses?



## Thoughts
- Variables are SS for functions; variables are functions that take zero arguments and always return a value. If variables reference other variables/functions, then the references are used once, immediately.
  - Being a functional language could help here



## Used Sugar
- `assign(myVar, myReturn, myParameters)` to `myVar(myParameters): myReturn`
- `String(myValue)` to `'myValue'`



## Basic Syntax
```
# Declaring and assigning variables, functions
myVar(): 42
myFun(a, b): a + b

# Objects, arrays, sets, maps
myArray(): Array(1, 2, 3)
mySet(): Set(1, 2, 3)
myMap(): Map(a(): 1, b(): 2, c(): 3)

# Strings
a(): add('Hello ', myVar())

# Math :(
myEval(a, b, c): add(a, sub(b, pow(c, 2)))
```



## Simplified Grammar
```
assignable: ID ( parameters ) : expression
parameters: parameters , parameter
parameter: value
```
