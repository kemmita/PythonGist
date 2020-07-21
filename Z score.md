```py
arra = np.array([12,454,23,98,45,66,90,77,15,93,41,150])

def z_score_transformation(x):
  return (x - np.mean(arra)) / np.std(arra,ddof=1)

z_scored = np.vectorize(z_score_transformation)(arr)
plt.title(display(Math('\huge z_{i} = \\frac{x_{i} - \overline{x} }{\\sigma_{x}}')))
plt.plot(z_scored)
```
