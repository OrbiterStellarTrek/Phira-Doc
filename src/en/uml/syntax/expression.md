# Expressions

Expressions are built from floats, variables, operators, and functions. They evaluate to a `Float`.

## Operators

- `+`: addition
- `-`: subtraction
- `*`: multiplication
- `/`: division
- `()`: parentheses for order of operations
- `==`: equal; result 1 if true, 0 otherwise
- `!=`: not equal; 1 if true, 0 otherwise
- `>`, `<`, `>=`, `<=`: comparison; 1 if true, 0 otherwise

## Functions

- `sin(x)`, `cos(x)`, `tan(x)`: trig (radians)
- `abs(x)`: absolute value
- `exp(x)`: exponential
- `atan2(x)`: arctangent
- `ln(x)`: natural log
- `sig(x)`: sign; 1 for +0 or positive, -1 for -0 or negative
- `step(x, y)`: step; 1 if x < y, else 0
- `floor(x)`, `ceil(x)`, `round(x)`: rounding
- `max(x, y...)`, `min(x, y...)`: max/min
- `clamp(x, min, max)`: clamp x to [min, max]

Trig and inverse trig use radians.
