## Elm - Basics

#### `main`

Every application in Elm starts on a `main` function that returns a static element or a signal of elements.

#### elm reactor

Elm `reactor` creates a server that compiles Elm on the fly.

#### Functions

* The first line is a function signature which is optional but recommended for clarity.
* The second line is the function declaration with the parameters `x` and `y`.
* The last line is the body of the function which returns the sum of the parameters.

```elm
add : Int -> Int -> Int
add x y =
  x + y
```

The function is called like this:

```elm
add 1 2
```

Parentheses are needed when you call a function with the result of another function call.

```elm
add 1 (divide 12 3)
```

##### The Pipe Operator

```elm
add 1 (multiply 2 3)
```

With the pipe operator looks like:

```elm
3
  |> multiply 2
  |> add 1
```

With a more complex example:

```elm
sum (filter (isOver 100) (map getCost records))
```

becomes:

```elm
records
  |> map getCost
  |> filter (isOver 100)
  |> sum
```