```py
import numpy as np
import pandas as pd
import seaborn as sb
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn import metrics

# The goal is to predice housing prices based off of the historical data provided below. 

# Create Data Frame
df = pd.read_csv('USA_Housing.csv')

# Create pairplot to identify potential usefull attributes/features, "x"
# sb.pairplot(df)

# Return array of col names and grab the attributes/features identified above.
df.columns

# Assign X to the features identified above
X = df[['Avg. Area Income', 'Avg. Area House Age', 'Avg. Area Number of Rooms',
       'Avg. Area Number of Bedrooms', 'Area Population']]

# Assign y to the label data
y = df.Price

# Create train test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.4, random_state=101)

# Create Linear Regression Model
lm = LinearRegression()

# Train Model
lm.fit(X_train, y_train)

# View coeficients and y intercept
cdf = pd.DataFrame(lm.coef_,X.columns,columns=['Coef'])
lm.intercept_

# Create predictions for the test data
predictions = lm.predict(X_test)

# Now we will want to compare our predictions against the actual prices stored in y_test and evalute the model
mae = metrics.mean_absolute_error(y_test, predictions)
mse = metrics.mean_squared_error(y_test, predictions)
rmse = np.sqrt(mse)
np.round(rmse,4)
```
