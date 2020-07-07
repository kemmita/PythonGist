```py
import numpy as np
import pandas as pd 
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv('diamonds.csv')

# Make the plot larger
plt.figure(figsize=(20,12))

# alpha = opacity and edgecolor=None simply cleans up the chart a bit
sns.scatterplot(x='carat', y='price', data=df, alpha=0.3, edgecolor=None);
```
