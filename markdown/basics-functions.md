## Elm - Basics | Functions

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

#### Type variables

This function takes a string and an array of strings and returns the index where the given string was found in the array or -1 if not found.
```elm
indexOf : String -> Array String -> Int
```

Here `String` is replaced with `a` and the signature of `indexOf` now takes a value of any type `a` and an array of that same type `a` and returns an integer.

```elm
indexOf : a -> Array a -> Int
```

Now states `indexOf` takes a value of any type `a` and an array of that same type `a` and returns an integer.

This is valid As long as types match.

```elm
switch : ( a, b ) -> ( b, a )
switch ( x, y ) =
  ( y, x )

switch (1, 2)
switch ("A", 2)
switch (1, ["B"])
```

#### Functions as Arguments

* This declares that `map` takes a function being `(Int -> String)`
* A list of integers
* Returns a list of strings

```elm
map : (Int -> String) -> List Int -> List String
```

The function provided to `map` must conform to the `(Int -> String)` signature.

```elm
map toString [1, 2, 3]
```

More commonly signatures use stand-ins instead of types that specific:

```elm
map : (a -> b) -> List a -> List b
```

