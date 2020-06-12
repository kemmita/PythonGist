1. below we will simply solve for x.
```python
// we first need to convert 2*x + 4 = 9 to 2*x + 4 - 9

import sympy as sym

x = sym.symbols('x')

expression = 2*x + 4 - 9

sym.solve(expression)


// we will not introduce another variable

y = sym.symbols('y')
x = sym.symbols('x')

expr = x/4 - x*y + 5

// define what var you want to solve for x or y
print(sym.solve(expr,y))
print(sym.solve(expr,x))
```
