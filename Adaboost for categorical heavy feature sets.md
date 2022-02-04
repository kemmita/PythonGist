1. Imports not all needed !!! :)
```py
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split, cross_val_score, GridSearchCV
from sklearn.linear_model import LinearRegression, Ridge, RidgeCV, Lasso, LassoCV, ElasticNet, LogisticRegression
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score, mean_absolute_percentage_error, SCORERS, confusion_matrix, accuracy_score, classification_report, plot_confusion_matrix, ConfusionMatrixDisplay
from sklearn.preprocessing import PolynomialFeatures, StandardScaler
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.ensemble import RandomForestClassifier, AdaBoostClassifier
```
2. Create DF and create X and y split prep
```py
df = pd.read_csv('mushrooms.csv')
df.describe().transpose().reset_index().sort_values('unique')

X = df.drop('class', axis=1)
y = df['class']
```
3. Get dummies for cat features
```py
X = pd.get_dummies(X,drop_first=True)
```
4. Train test split and create AdaModel
```py
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.15, random_state=101)
model = AdaBoostClassifier()
```
5. Use Grid Search to locate optimal number of estimators/stumps
```py
grid = GridSearchCV(model,{'n_estimators':[*range(1, len(X.columns), 1)]})
grid.fit(X_train,y_train)
grid.best_params_
```
6. Create new model with optimal stump number and make predictions
```py
model = AdaBoostClassifier(n_estimators=20)
model.fit(X_train,y_train)
preds = model.predict(X_test)
print(classification_report(y_test, preds))
```
7. Analyze feature importance
```py
model.feature_importances_
feats = pd.DataFrame(index=X.columns, data=model.feature_importances_,columns=['Feature Importance'])
feats[feats['Feature Importance'] >0].sort_values(by='Feature Importance')
```
