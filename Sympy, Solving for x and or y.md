1. below we will simply solve for x.
```python
// we first need to convert 2*x + 4 = 9 to 2*x + 4 - 9

import sympy as sym
from IPython.display import display,Math

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

//solve for q 3q + 4/q + 3 = 5q + 1/q +1
//convert for sympy change thew = to a - and then any + must become a - or you could wrap the entire left side in ()
eq = 3*q + 4/q + 3 - 5*q - 1/q - 1

// the only thing we need to solve below is sym.solve(q) the rest is to make the output in notebook look pretty
display(Math(sym.latex(sym.solve(eq))))

//once we run 
res = sym.solve(eq)
// we can access it like so res[0]
```
