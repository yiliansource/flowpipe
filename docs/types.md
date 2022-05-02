# Types

Flowpipe offers the usual built-in types you would expect from a programming language. Note that all types are treated as value types, to promote the usage of pipes.

## Primitives

| Keyword | Default |
| --- | --- |
| `number` | 0 |
| `boolean` | `FALSE` |
| `string` | `""` |

## Tuples

Tuples are a handy way to pass additional data down your pipes instead of just a singular value. They are created via

```
(foo, bar, ...)
```

and can take any number of values. If you then need to consume a specific value of the tuple, you can use a _tuple-accessor_ (0-indexed):

```
(TRUE, 3, "Hello!") > @1 > print         # prints "3".
```

## Lists

## Checking types

You can check the type of a variable using the `typeof` method.

```
def typeof(x: object) -> boolean
```

For example:

```
"Hello World!" > typeof > print      # prints "string".
```

Built-in methods will commonly verify the types of the passed parameters, and might produce a `TypeMismatchError` if expected and received types do not align.