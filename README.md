# Assginment-no-3
#load data
data = pd.read_csv("WPRWeekly_2.csv")
data.head()

print (data['Rural Male + Rural Female'])
print (data['Rural Male + Rural Female'].isnull())

print (data['Urban Male'])
print (data['Urban Male'].isnull())

missing_values=["NAN","NA","--"]
dataset = pd.read_csv("WPRWeekly_2.csv",na_values=missing_values)

missing_values=["NA","NAN","--"]
data = pd.read_csv("WPRWeekly_2.csv",na_values=missing_values)
print (data['Urban Male'])
print (data['Urban Male'].isnull())

print (data.isnull().sum())

print (data.isnull().sum().sum())

print (data['Rural Male + Rural Female'])
median = data['Rural Male + Rural Female'].median()
print (median)
data['Rural Male + Rural Female'].fillna(median, inplace=True)
print(data['Rural Male + Rural Female'])

print (data['Urban Male'])
median = data['Urban Male'].median()
print (median)
data['Urban Male'].fillna(median, inplace=True)
print(data['Urban Male'])

x = data[['Rural Male','Rural Female']]
y = data['Rural Male + Rural Female']

x

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2)

x_train

from sklearn.linear_model import LinearRegression
clf = LinearRegression()

clf.fit(x_train,y_train)

clf.predict(x_test)

y_test

clf.score(x_test,y_test)

data.corr()

data.mean()

data.max()

data.describe()

import matplotlib.pyplot as plt
#data=data.reindex(['a','b','c','d','e','f','g','h','i','j','k'])

X = data["Rural Male + Rural Female"]
Y = data["Urban Male"]
plt.scatter(X, Y, label="stars", color="red",
            marker="1", s=30)
plt.title("Scatter Plot")
plt.xlabel("States")
plt.ylabel("Count")
plt.show()
