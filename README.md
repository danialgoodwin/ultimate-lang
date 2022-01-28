# ultimate-lang
What I want in my ultimate future programming language

Similar to Kotlin + Python.

This repo will contain all my thoughts about language design, and reasons for choosing features and trade-offs.



## Basic Syntax

```
@ultimate-mode: dynamic, interpreted  # Options: dynamic/static, interpreted/compiled, prefer-speed/prefer-size, log-error/log-warn/log-info/log-debug

a: 40
a +: 2
b: 'foo'
c: '3' as number

b.loop { i, c ->
    print '$i: $c'
}

c.loop { i ->
    print '$i: $c'
}

@memoize(1 kb)  # Options: @inline, @lazy, @memoize
doMath(a, b): {
    return 4 * a + b^2
}
```



## Features
- Focused (no boilerplate)
- Extension functions (easy DSL)



## Open Questions
- What would a language look like with no syntactic sugar? How simple could we make that language?
- What if no `for` loops? Can we turn all of these usages into something else?

### Trade-offs
- Readability for new users vs conciseness for familiar users
  - Ex: `print('text', newline='\n')` vs `println('text)`
  - Ex: `` vs ``
- Consistency vs syntactic sugar
  - Ex: `print('text')` vs `print 'text'`
  - Ex: `loop() { ... }` vs `loop { ... }`
  - Ex:   `42 as kb` vs `42 kb`
- Explicit vs implicit conversions
  - Ex: `int a: '5' as int` vs `int a: '5'`
  - Ex: `float b: 5f` vs `float b: 5`
  - Ex: `TypeA a: typeB as TypeA` vs `TypeA a: typeB`
- Tradition vs re-think
  - Ex: `var x = 2` vs `var x: 2`
  - Ex: `x += 2` vs `x +: 2`
  - Ex: `for e in elements { ... }` vs `loop e in elements { ... }` vs `elements.each { ... }`
  


## Design Decisions
- Discuss: Assignment operator syntax
- Think about what's easy to type on common keyboards (internationally)



## Experimental
Eventually, these ideas will be moved to more specific areas.

Maybe call different levels of the language
 a0 for compiled code for specific architecture
 a1 for bytecode running in VM
 a2 for interpreted code

Or
Have the levels for how low-level the language is, like for compiler, and compiler-compiler, and compiler-compiler-compiler

- Rather than using the `override` keyword for methods, maybe have something like `extends` so that the super-class can use more aspect-oriented programming to determine when super.myMethod() is called, and it can do something before and after. If super is called explicitly, then treat the code differently?
    - Meh

- Language config can either go at the top of a file, or in a .langconfig at the project root, or perhaps in a global config in ~/.config/lang/config? Meh to the last one bc hidden dependency and not in version control.



## Resources
