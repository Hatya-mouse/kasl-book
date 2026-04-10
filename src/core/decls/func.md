# Function

`func` statement declares a function in the top level or struct declarations.

Functions can have multiple parameters and single return value. If no return type is specified, the function is expected to return no value.
Every parameters can have an argument label for clarity.

## Syntax

```
// Basic
func <name>() { }

// With parameters
func <name>(<param>: <Type>) { }

// With return value
func <name>(<param>: <Type>) -> <Type> { }

// With argument label
func <name>(<label> <param>: <Type>) { }

// With default value
func <name>(<param> = <default>) { }

// Static function
static func <name>() { }
```

## Example 1 --- Basic

The program below declares a function called greet, which takes no parameters and returns nothing.
Note that the program cannot be compiled because it does not have a `main` function.

```kasl
func greet() {
    // Do something
}
```

## Example 2 --- Parameters and Return Value

The program below declares some functions with parameters and return types, and they can be called as shown in the `main` function.

```kasl
import std

func add(lhs: Int, rhs: Int) -> Int {
    return lhs + rhs
}

func multiply(times a: Int, by b: Int) -> Int {
    return a * b
}

func increment(value: Int = 0) -> Int {
    return value + 1
}

// Use the declared functions!
func main() {
    add(1, 2) // 3
    multiply(times: 3, by: 4) // 12
    increment() // 1
    increment(10) // 11
}
```

## Example 3 --- Static Function

The program below creates a static function called `unit`, which can be called by `Circle.unit()` using its belonging type name `Circle`.

```kasl
struct Circle {
    var radius = 0.0

    static func unit() -> Circle {
        var c = Circle()
        c.radius = 1.0
        return c
    }
}

func main() {
    let unit_circle = Circle.unit()
}
```
