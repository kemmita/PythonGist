1. Imports
```py
import numpy as np
import pandas as pd
import matplotlib as plt
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import classification_report,confusion_matrix
```
2. Bring in data and clean
```py

```

3. Elbow method to obtain k value
```py
# Read in data
df_2 = pd.read_csv('knn_data',index_col=0)

# Standardize your feature columns "IMPORTANT" for KNN
scaler = StandardScaler()
scaler.fit(df_2.drop('TARGET CLASS', axis=1))
scaled_features = scaler.transform(df_2.drop('TARGET CLASS', axis=1))

# Specify our features and create a dataframe
df_feat = pd.DataFrame(scaled_features, columns=df_2.columns[:-1])

# Create train test split
X_train, X_test, y_train, y_test = train_test_split(df_feat, df_2['TARGET CLASS'], test_size=0.3, random_state=101)

#  We will now use the elbow method to obtain the "best" k value
error_rate = []

for i in range(1,40):
    # create classifier with i/k neighbors    
    knn_classifier = KNeighborsClassifier(n_neighbors=i)
    # Train Classifier
    knn_classifier.fit(X_train, y_train)
    # Make prediction
    pred_i = knn_classifier.predict(X_test)
    error_rate.append(np.mean(pred_i != y_test))
   
plt.plot(range(1,40),error_rate,linestyle='dashed',marker='o')
idx = np.argmin(error_rate)
best_k = error_rate[33]
```

4. Train model and make predicitons
```py
# Instantiate KNN CLasifier object
knn_classifier = KNeighborsClassifier(n_neighbors=best_k)

# Train Classifier
knn_classifier.fit(X_train, y_train)

# Make prediction
pred = knn_classifier.predict(X_test)
```

5. Evaluate predictions
```py
# Evaluate prediction
print('Confusion Matrix')
print(confusion_matrix(y_test,pred))
print('Classification Report')
print(classification_report(y_test,pred))
```
