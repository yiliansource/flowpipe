# Flow

Flowpipe is non-convential in its style of code execution. The execution pointer can be freely redirected around the source code and is not restricted to right-to-left or top-to-bottom evaluation.

Consider the following (identical) examples:

```
3 > ++ > * 2 > -- > print

3 > ++ > * 2
          v
 print < --

# both print "8".
```

This gives you the possibility to structure your code in a creative fashion, approaching implementations in an unusual, fresh manner.

## The execution path

The way that the path is picked relies on the geometric structure of the source code. Once an expression was evaluated, the runtime will attempt to locate the next adjacent expression to execute, determined by a pipe (`>`, `<`, `v`, `^`) leading into it. If no adjacent expression is found, execution of the current node path will terminate.

### Conditionals



### The identity function

The _identity function_ `.` always returns the value piped into it, hence it proves useful when navigating corners, for example.

### Bridge pipes

Occasionally you might come across the need to have pipes cross over each other. If you have a structure like

```
  ^
>   >
  ^
```

then pipe navigation will work without issues, however if pipes explicitly cross paths, like

```
  ^
> ^ >
  ^
```

then the pipe executing from left-to-right will turn upwards instead of being passed further on to the right. The solution for this is the _bridge pipe_ (i.e. `>>`) which skips all regular pipes until it finds a matching bridge pipe in the same direction.

```
   ^
>> ^ >>
   ^
```

## Function evaluation

The usual approach to evaluate functions in Flowpipe is not by actually calling them with arguments explicitly, but instead by piping the data directly into them, as seen in the example above.

However, if the need arises, you can also evaluate functions explicitly, using the `@` parameter:

```
"Hello World!" > print(@)
```

However, doing this excessively is advised against.