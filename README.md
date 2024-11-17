# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 ```
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]
sns.lineplot(x=x,y=y)
```
![Screenshot 2024-11-17 170521](https://github.com/user-attachments/assets/cd4489b7-6970-4e41-b490-4ff991a1cf96)
```
df = sns.load_dataset("tips")
df
```
![Screenshot 2024-11-17 170631](https://github.com/user-attachments/assets/e43df0b8-c727-44d2-a1ee-d4d9f16b34a8)
```
sns.lineplot(x="total_bill",y="tip", data=df, hue="sex", linestyle='solid', legend="auto")
```
![Screenshot 2024-11-17 170716](https://github.com/user-attachments/assets/1b96c08d-d81a-44f8-98c9-dd89cdf66aa7)
```
x=[1, 2, 3, 4, 5]
y1=[3, 5, 2, 6, 1]
y2=[1, 6, 4, 3, 8]
y3=[5, 2, 7, 1, 4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel("Y Label")
```
![Screenshot 2024-11-17 170835](https://github.com/user-attachments/assets/141964ed-b46d-4b2b-8dc0-ed8aeee15545)
```
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip = tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![Screenshot 2024-11-17 170914](https://github.com/user-attachments/assets/d701a0e1-2723-4686-8830-a26844f634c5)
```
avg_total_bill = tips.groupby('time')['total_bill'].mean() 
avg_tip=tips.groupby('time') ['tip'].mean()
p1= plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip', width=0.4)
```
![Screenshot 2024-11-17 170950](https://github.com/user-attachments/assets/a25fb66c-0c6f-4710-819a-ad1a181b3c8b)
```
years=range(2000, 2012)
apples=[0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939] 
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![Screenshot 2024-11-17 171101](https://github.com/user-attachments/assets/721dcd06-e785-4558-804d-f7fb7c48a34d)
```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the Week')
plt.ylabel("Total Bill")
plt.title('Total Bill by Day and Gender')
```
![Screenshot 2024-11-17 171157](https://github.com/user-attachments/assets/da12f5d8-6b0b-4687-bc76-e704b8fa1a7c)
```
tit=pd.read_csv("titanic_dataset.csv")
tit
```
![Screenshot 2024-11-17 171245](https://github.com/user-attachments/assets/2c7b91ae-bd29-482c-8237-b0f8a6a123f3)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow') 
plt.title("Fare of Passenger by Embarked Town")
```

![Screenshot 2024-11-17 171333](https://github.com/user-attachments/assets/5478aaf8-514a-49f2-aad8-1d0e32de6ccd)
```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked', y='Fare', data=tit, palette='rainbow', hue='Pclass') 
plt.title("Fare of Passenger by Embarked Town, Divided by Class")
```
![Screenshot 2024-11-17 171445](https://github.com/user-attachments/assets/ff910e85-392e-4bf4-81ef-47a03b811764)
```
tips=sns.load_dataset('tips')
sns.scatterplot(x='total_bill', y='tip', hue='sex', data=tips)
plt.xlabel('Total Bill')
plt.ylabel("Tip Amount")
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```

![Screenshot 2024-11-17 171526](https://github.com/user-attachments/assets/9872170e-cd6c-4fb7-b378-6cb77a51683c)
```
num_var = np.random.randn(1000)
num_var=pd.Series(num_var, name = "Numerical variable")
num_var
```

![Screenshot 2024-11-17 171559](https://github.com/user-attachments/assets/5f9429ed-c293-46b1-be57-4ffaeb546970)
```
sns.histplot(data = num_var, kde = True)
```
![Screenshot 2024-11-17 171632](https://github.com/user-attachments/assets/3947b7fe-68d0-4107-b899-5dddf2e343e2)
```
df=pd.read_csv("titanic_dataset.csv")
sns.histplot(data=df,x="Pclass", hue="Survived", kde=True)
```
![Screenshot 2024-11-17 171709](https://github.com/user-attachments/assets/6d0ef591-269a-412d-87ba-1aa6b988e143)
```
tips=sns.load_dataset('tips')
sns.boxplot(x=tips['day'], y=tips ['total_bill'], hue=tips['sex'])
```
![Screenshot 2024-11-17 171747](https://github.com/user-attachments/assets/74979d41-efe9-4163-8543-da2c7591632b)
```
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, boxprops={"facecolor": "lightblue", "edgecolor": "darkblue"},
whiskerprops={"color": "black", "linestyle": "--", "linewidth": 1.5}, capprops={"color": "black", "linestyle": "--", "linewidth": 1.5})
```
![Screenshot 2024-11-17 171816](https://github.com/user-attachments/assets/54496c8f-471f-4d20-8dd5-25818b74e8ef)
```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6, palette="Set3", inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![Screenshot 2024-11-17 171858](https://github.com/user-attachments/assets/1283c46b-3265-474e-b0db-722f96666c35)
```
mart=pd.read_csv("titanic_dataset.csv")
mart
```
![Screenshot 2024-11-17 172016](https://github.com/user-attachments/assets/3a6c5511-cee7-44d0-b9dd-fe1646e9f405)
```
mart=mart[['PassengerId', 'Survived', 'Age', 'Name', 'Ticket', 'Embarked']] 
mart.head(10)
```
![Screenshot 2024-11-17 172050](https://github.com/user-attachments/assets/d996b32d-6333-407d-89d3-890e8d79a9ae)
```
sns.kdeplot(data=mart,x='PassengerId')
```
![Screenshot 2024-11-17 172123](https://github.com/user-attachments/assets/24ff2185-5270-4647-b4af-a0317229d67f)
```
sns.kdeplot(data=mart)
```
![Screenshot 2024-11-17 172215](https://github.com/user-attachments/assets/092ac929-6ac4-4c6d-a3c7-373aff9f3e00)
```
sns.kdeplot(data=mart,x='PassengerId',hue='Survived',multiple='stack')
```
![Screenshot 2024-11-17 172255](https://github.com/user-attachments/assets/0966787b-e89d-4179-8858-d2490dc29069)
```
sns.kdeplot(data=mart,x='PassengerId',y='Survived')
```
![Screenshot 2024-11-17 172321](https://github.com/user-attachments/assets/9e9e3f9d-c951-4ffe-9447-34c91b44d161)
```
data = np.random.randint(low = 1, high = 100, size = (10,10))
hm=sns.heatmap(data=data,annot=True)
```

![Screenshot 2024-11-17 172404](https://github.com/user-attachments/assets/0f0331f7-2b72-4796-98e8-4e2ed8fb459a)


# Result:
Thus, all the data visualization techniques of seaborn has been implemented.
