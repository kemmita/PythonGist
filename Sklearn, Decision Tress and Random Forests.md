```py
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report,confusion_matrix
```

```py
# Import data
df = pd.read_csv('loan_data.csv')

# Get dummies
df = pd.get_dummies(df, columns=['purpose'],drop_first=True,)

# Grab features and label
X = df.drop('not.fully.paid',axis=1)
y = df['not.fully.paid']

# Create train test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```

```py
# Create single decision tree
d_tree = DecisionTreeClassifier()

# Train tree
d_tree.fit(X_train,y_train)

# Get predictions
d_tree_pred = d_tree.predict(X_test)

# View perfomance
print(classification_report(y_test, d_tree_pred))
confusion_matrix(y_test,d_tree_pred)
```

```py
# Create Random Forest with 300 decision trees
rf = RandomForestClassifier(n_estimators=300)

# Train model
rf.fit(X_train, y_train)

# Get predicitons
rf_pred = rf.predict(X_test)

# View perfomance
print(classification_report(y_test, d_tree_pred))
confusion_matrix(y_test,d_tree_pred)
```
