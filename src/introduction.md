# KASL

KASL is a statically typed programming language built for audio synthesis and creating audio effects.
Its syntax is heavily inspired by [Swift](https://en.wikipedia.org/wiki/Swift_(programming_language)), but not based on it and does not have complex memory management system like ARC.

## Example of KASL

For those who want to grasp the syntax, here's an example of KASL code.

```kasl
// Import the std library.
import std
// You can specify the subdirectories just by using "/" in the import statement.
import math/float

// Declare a struct named Thing.
struct Thing {
    // Struct fields.
    var a = 0
    
    // Static functions, which can be called like "Thing.zero()".
    static func zero() -> Int {
        return 0
    }
    
    // Member functions, in which "self" keyword can be used.
    func decrement(amount: Int) {
        self.a = self.a - amount
    }
}

// Name the any type you want.
typealias Vector2 = [Float; 2]

// Custom operator definitions.
operator infix ** {
    precedence: 95,
    associativity: right
}

operator prefix ++ {
    precedence: 110
}

operator postfix % {
    precedence: 110
}

// Custom operator implementations.
func infix **(lhs: Float, rhs: Float) -> Float {
    return float.pow(lhs, rhs)
}

func prefix ++(operand: Int) -> Int {
    return operand + 1
}

func postfix %(operand: Float) -> Float {
    return operand / 100.0
}

// Input variables.
input float_in = 0.0
input int_in = 0
input bool_in = false
input thing_in = Thing()

// Output variables.
output float_out = 0.0
output int_out = 0
output bool_out = false
output thing_out = Thing()

// State variables.
state float_state = 0.0
state int_state = 0
state bool_state = false
state thing_state = Thing()

// Constants.
let pi = 3.1415926535

// The main function, which will be called when processing the program.
func main() {}
```
