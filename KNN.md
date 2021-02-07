```py
import numpy as np
import pandas as pd
from IPython.display import Math,display 
from sklearn import preprocessing

names = ['Ajay', 'Mark', 'Russ', 'Samantha', 'Kayla', 'Steven', 'Caleb', 'Kyle', 'Rachel', 'Sant']
age = [32,40,16,34,55,40,20,15,55,15]
gender = ['m', 'm', 'm', 'f', 'm', 'm','f','m','f','m']
sport = ['football', 'neither', 'bascketball','bascketball','neither','bascketball','neither','bascketball','football','football']
d = {'Name': names, 'Age': age, 'Gender': gender,'Sport':sport}
df = pd.DataFrame(data=d)

# Convert gender to numeric values ie "0, 1"
gender_n = pd.get_dummies(df['Gender'],drop_first=True)

# Convert sport to numeric
sport_n = le.fit_transform(np.array(df['Sport']))

df = pd.concat([df, gender_n, pd.DataFrame(data=sport_n)], axis=1)

df.drop(['Gender', 'Sport'],axis=1,inplace=True)

df.rename(columns={'m': 'Gender', 0: 'Sport'}, inplace=True)


# Predict the sport Angelina is most likely to favor
angelina = {'age': 5, 'gender': 0}

k = 3


# We will use the Euclidean distance's 
display(Math(' d(q,p) = \\sqrt{\sum\limits_{i=1}^{N}(qi -pi)^2}'))

def knn(df, person, K):
    q1 = np.array(np.square(person['age'] - df['Age']))
    q2 = np.array(np.square(person['gender'] - df['Gender']))
    results = np.array(np.sqrt(q1 + q2))
    idx = np.argpartition(results, k)
    k_results = np.array(df.iloc[idx[:3]])
    return np.argmax(k_results[:, 3])
    
knn(df, angelina, k)
```
