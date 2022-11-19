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

- `loop` and `loopi` (to include index?) vs just include another param and it will exist automagically? But, what if looping through a map with key and value params already, or looping through a deconstructed Tuple3? Don't need to make the API bigger with `loopi`

- Programming language to replace bash and be good for general large programs. Is Kotlin good enough?

- Consider: "So you want to write a package manager"
    - https://medium.com/@sdboyer/so-you-want-to-write-a-package-manager-4ae9c17d9527
    - https://news.ycombinator.com/item?id=11088125

- Live coding 'always'
- At least a basic version of 'everything' should be available in the standard library, like: server, web pages, gui, json, xml, csv, markdown, code generator, video, ai, machine learning, math, statistics, art, image generation, file manipulation, database/SQL, SQLite, regex, animation, standards (sort by usage? popularity?)
    - When compiling, do 'tree-shaking' to not have all the extra code
    - tables/cells in the code, also: images, maybe animations
- There should be a good build system with dependency manager for the language. Though, should likely allow for plugins to optionally use the common interface.
    - It's nice to have a simple one built-in so that it's extremely easy to get started... Only one download required. Definitely make it easy for students for a class to get started with.
- Nice to have: Ability to build simple apps right away. Something needs to be the 'killer' app for the language, like Rails is for Ruby.



## Resources
