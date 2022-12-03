
What if there no syntactic sugar in this programming language?

The goal of this project is to see what a programming language could look like with no syntactic sugar (SS). Could it be simple if designed well?
- Probably Lisp. But, what if it isn't all parentheses?

The purpose of this experiment is to expliticly write down what SS we take for granted, and to know what SS we would really want in our 'ultimate programming language'. In the course of this exercise, can we find a good/better way to add SS to a language? What does it take for a 4th generation language to become a 5th generation language?



## Thoughts
- The most no-sugar language would probably be an AST (abtract syntax tree). Parsers usually create these.
- Variables are SS for functions; variables are functions that take zero arguments and always return a value, and that return value is saved. If variables reference other variables/functions, then the references are used once, immediately.
  - Being a functional language could help here



## Used Sugar
- `assign(myVar, myReturn, myParameters)` to `myVar(myParameters): myReturn`
- `String(myValue)` to `'myValue'`
- TODO: Loops?


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

Or (but, this may be harder to read?):
```
assign a 1
assign b inputs foo bar do
    comment TODO
end
```


## Simplified Grammar
```
assignable: ID ( parameters ) : expression
parameters: parameters , parameter
parameter: value
```
