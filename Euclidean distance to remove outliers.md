```py
display(Math('\huge distance_{a,b} = \\sqrt{(a_{x} - \overline{a})^{2} + (a_{y} - \overline{b})^{2}}'))

a = np.array([12,23,66,77,45,10,18000,455,1000,200,56])
b = np.array([12,230,668,7,451,1,19000,451,1004,20,52])

# collect the data mean
data_mean = [np.mean(a), np.mean(b)]

# Initialize an empty np array
N = len(a)
distance = np.zeros(N)

# Collect the distance
for i in range(N):
  distance[i] = np.sqrt( np.power(a[i] - data_mean[0], 2) + np.power(b[i] - data_mean[1], 2) )

# Convert to zscores
distance_z = stats.zscore(distance) 

threshold = 3 

plt.plot(distance_z,'k^',markerfacecolor='w',markersize=12)
plt.plot([0,33],[threshold,threshold],'r--')
plt.plot([0,33],[-threshold,-threshold],'r--')
plt.xlabel('var x')
plt.ylabel('var y')
plt.show()

# Remove outliers



```
