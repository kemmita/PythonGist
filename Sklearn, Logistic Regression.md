```py
import numpy as np
import pandas as pd
import seaborn as sb
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, confusion_matrix

# Create Data Frame
df = pd.read_csv('titanic_train.csv')

# Drop unuseful cols
df.drop(['Name','Ticket','PassengerId'],inplace=True,axis=1)

# To identify null columns that may need to be removed or provided with a default value, we can use Seaborns heatmap to spot nulls
# sb.heatmap(train.isnull())

# Drop cols identified above, the Cabin data has so much missing data that it makes sense to drop it here.
df.drop('Cabin', axis=1,inplace=True)

# Provide default vals for Age identified above. We will retun the avg age depending on class.
def impute_age(cols):
  Age = cols[0]
  Pclass = cols[1]

  if pd.isnull(Age):
    if Pclass == 1:
      return np.mean(df[df.Pclass == 1].Age)
    elif Pclass == 2:
      return np.mean(df[df.Pclass == 2].Age)
    else:
      return np.mean(df[df.Pclass == 3].Age)
  else: 
    return Age

df.Age = df[['Age', 'Pclass']].apply(impute_age,axis=1)

df.dropna(inplace=True)

# Create dummy vars for categorical data
sex = pd.get_dummies(df['Sex'],drop_first=True)
embark = pd.get_dummies(df['Embarked'],drop_first=True)

# Take the two new dfs and concat them to the train df
df = pd.concat([df, sex, embark],axis=1)

# Drop the categorical cols that were converted to dummy above.
df.drop(['Embarked','Sex'],axis=1,inplace=True)

# Define Label
y = df['Survived']

# Define Features
X = df[['Pclass', 'Age', 'SibSp', 'Parch', 'Fare', 'male', 'Q','S']]

# Create train test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=101)

# Create instance of logistic regression model
logmodel = LogisticRegression(max_iter=1000)

# Train/fit the model
logmodel.fit(X_train, y_train)

# Get predictions
predictions = logmodel.predict(X_test);

# Evalute the model's performance.
print(classification_report(y_test,predictions))
confusion_matrix(y_test,predictions)
```
