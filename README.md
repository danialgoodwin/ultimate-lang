# ultimate-lang
What I want in my ultimate future programming language

Similar to Kotlin + Python.



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
  


## Design Decisions
- Discuss: Assignment operator syntax



## Resources
