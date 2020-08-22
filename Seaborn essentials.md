```py
import matplotlib.pyplot as plt
import seaborn as sb

tips = sb.load_dataset('tips')

# Essential Plots
sb.distplot(tips['total_bill'], kde = False, bins=40)
sb.pairplot(tips,hue='sex')
sb.regplot(x='total_bill',y='tip',data=tips)
sb.scatterplot(x=tips['total_bill'],y=tips['tip'])
sb.barplot(x='sex',y='total_bill',data=tips,estimator=np.std)
sb.countplot(x='sex',data=tips)
sb.lmplot(x='total_bill',y='tip',data=tips)
```
