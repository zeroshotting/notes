---
created: ""
confidence level: 
review count: 0
---
# Abstraction
---
Abstraction can be thought of as building things on top of smaller things. This could be in terms of objects or concepts. In the case of computer programs abstraction. We go from fundamental building blocks and then continue to build more _complex_ structures.

```
app <- hl lang <- ll lang <- machine lang/arch <- logic gates <- transistors
```

# Functions
---
A function is a relationship that has zero or more inputs and has one output. Functions _always_ produce the same outputs given the same inputs. Functions are pretty well understood by theoreticians and it's easy to reason about them and prove theorems about them. The overall state of a program does not affect the behavior of a function so it's easier to use parallelism.

$f(x) = 2x + 6$ and $g(x) = 2(x + 3)$ are the same function but different procedures (code implementations). The behave the same way in terms of input and output but they have different steps. Functions are implemented as algorithms in computers, a sequence of steps.

Scheme does _applicative order evaluation_. All the sub-expressions are evaluated which converts argument expressions to argument values. The formal parameters in the body of the procedure are replaced with actual argument values. There are other ways of doing things such as _normal order evaluation_. In normal order, when a procedure is called the actual argument expressions are substituted into the body. Nothing is evaluated until a primitive is called.

insert example here

# More Context
---

# Further  Reading
---