---
created: 2025-05-07
confidence level: high
review count: 0
---
# Basics of Scheme (Applicable to the LISP family)
---
- Scheme syntax is basically just [S-expressions](https://en.wikipedia.org/wiki/S-expression) (also known as symbolic expression, sexp, or sexpr).
- An S-expression is defined as either an atom of the form `x` or an expression of the form `(x . y)` where x and y are S-expressions.
- S-expressions can be fully expressed as binary trees. This is due to their recursive nature. For example, in Scheme, `(a b c)` is just syntactic sugar for `(cons 'a (cons 'b (cons 'c '())))`.
- Each node in the resulting binary tree is a `cons` cell, the left child is the value (`car`), and the right child is the rest of the list (`cdr`).
- Example of scheme statements:
	- `(* 2 3)`
	- `(display 'hello)`
	- `(define (square x) (* x x))`
- Sub-expressions are usually evaluated first, except in the case of special forms which override this behavior. Special forms include `cond`, `if`, `define`, `lambda`, `quote`, `seti`, `begin`, `and/or`, `let`.
- In Scheme, characters are written like this: `#\<char-name>` e.g. `#\a`, `#\1`, etc.
- `if` statements are another special form.
- `cond` looks very handy. It's structure is like so:

```scheme
(cond 
		((<condition-1>) (<consequent-1>))
		((<condition-2>) (consequent-2>))
		...
		((<condition-n>) (consequent-n>))
		(else (<alternative>)))
```

- `if` is handy as well but works slightly differently. Only one branch is evaluated:
```scheme
(if (<condition>) (<consequent>) (<alternative>))
```

- ' is a quote, used to prevent evaluation.
- <span>&grave;</span> is quasiquote, used for constructing expressions with optional evaluation.

# Further Reading
---
- [[Structure and Interpretation of Computer Programs]]