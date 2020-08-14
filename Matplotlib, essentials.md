```py
import matplotlib.pyplot as plt

# Get Data
x_woman = [200,100,23,45,66,98]
y_woman = [35,30,10,15,24,32]

x_men = [200,100,23,45,66,98]
y_men = [30,20,8,12,24,22]

# Instantiate fig
fig = plt.figure()

# Define size of chart
axes = fig.add_axes([0.1,0.1,1.3,1.3])

# Plot your data, the labels will be cited in the legend that we will instantiate below
axes.scatter(x_woman,y_woman, label='Women', color='hotpink')
axes.scatter(x_men,y_men, label='Men', color='blue')
axes.legend()

# Define x and y label
axes.set_xlabel('Total Sale')
axes.set_ylabel('Tip')

# Set x and y limits for the axis
axes.set_xlim(0,1000)
axes.set_ylim(0,100)
```
