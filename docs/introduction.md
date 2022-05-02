# Introduction

Flowpipe is a semi-esoteric programming language, based on the idea of function composition.

## Hello World

Very minimal.

```
"Hello World!" > print
```

Note that we do not have a `main`-block or something similar. Flowpipe will automatically execute top-level statements, so essentially your entire source file is treated as a `main`-block.

## Running

Flowpipe source files usually have a file extension of `*.fp`. If you saved your "Hello World" program into `hello.fp`, you can now execute it with

```console
$ flowpipe hello.fp
```

The interpreter will perform a static compilation check to ensure that the expression tree can be built correctly. If you only want to check for errors, you can run

```console
$ flowpipe hello.fp -b
```

## Additional notes

Flowpipe is dynamically typed - you cannot define type constraints in your code. However, for the purposes of clarity, the documentation will often provide type hints for methods in the form of

```
def foo(bar: object) -> object
```