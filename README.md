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

```
Developed by: AMAN SINGH
Register no: 212224040020
```

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
<img width="506" alt="Screenshot 2025-04-21 at 9 17 40 AM" src="https://github.com/user-attachments/assets/023851ca-5f70-438e-b4b3-298253a57548" />

```
df=sns.load_dataset('tips')
df
```
<img width="461" alt="Screenshot 2025-04-21 at 9 17 56 AM" src="https://github.com/user-attachments/assets/0d2c9c48-8ecf-4d1a-994e-c867f2c8eae9" />


```
sns.lineplot(x="total_bill",y="tip",data=df, hue="sex",linestyle="solid" ,legend="auto")
```
<img width="520" alt="Screenshot 2025-04-21 at 9 18 05 AM" src="https://github.com/user-attachments/assets/d57613e1-f946-49d3-bf1a-14c1317ee4fc" />

```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]

sns.lineplot(x=x,y=y1,label="line1")
sns.lineplot(x=x,y=y2,label="line2")
sns.lineplot(x=x,y=y3,label="line3")
plt.title("Multi-line-plot")
plt.xlabel("x-axis")
plt.ylabel("y-axis")
plt.legend()
plt.show()

```
<img width="465" alt="Screenshot 2025-04-21 at 9 18 15 AM" src="https://github.com/user-attachments/assets/45bdedb9-8994-4777-a986-309ff3a49682" />


```
import seaborn as sns
import matplotlib.pyplot as plt
# Load the tips dataset
tips = sns. load_dataset ('tips')
#Calculate the average total bill and tip for each day of the week
avg_total_bill = tips.groupby('day')['total_bill'].mean ()
avg_tip = tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
# Set the labels and title
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
<img width="538" alt="Screenshot 2025-04-21 at 9 18 26 AM" src="https://github.com/user-attachments/assets/59c68989-2a52-4937-9fd4-c9bed0f1c9ae" />

```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()
# Create a grouped bar chart
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom = avg_total_bill, label='Tip', width=0.4)
```
<img width="461" alt="Screenshot 2025-04-21 at 9 18 36 AM" src="https://github.com/user-attachments/assets/42111a08-1f24-4f3f-a412-0b96381bb725" />
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/titanic_dataset (1).csv")
df.head()
```
<img width="598" alt="Screenshot 2025-04-21 at 9 19 20 AM" src="https://github.com/user-attachments/assets/cbfd9d48-c1f3-4019-805c-b55acab260e3" />


```
plt.figure(figsize=(8,5))
sns.barplot(x='Embarked',y='Fare',data=df,palette='rainbow')
plt.title("Fare Of Passenger By Embarked Town")
```

<img width="546" alt="Screenshot 2025-04-21 at 9 19 29 AM" src="https://github.com/user-attachments/assets/381194bf-743a-4e59-afd9-f82065a1425a" />

```
import numpy as np
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)

plt.figure(figsize=(8, 5))
sns.histplot(marks, bins=10, kde=True, color='skyblue')
plt.title("Histogram of Marks")
plt.xlabel("Marks")
plt.ylabel("Frequency")
plt.grid(True)
plt.show()
```
<img width="552" alt="Screenshot 2025-04-21 at 9 19 38 AM" src="https://github.com/user-attachments/assets/c1be70a6-9ecd-40ea-bcc4-2ea3aee38433" />

```
sns.scatterplot(x="Age", y="Fare", data=df)
plt.title('Scatterplot of Age vs Fare')
plt.show()
```
<img width="455" alt="Screenshot 2025-04-21 at 9 19 46 AM" src="https://github.com/user-attachments/assets/34b558b2-17f4-469e-9a40-718aeb228e57" />

```
plt.figure(figsize=(8, 5))
sns.histplot(data=df, x='Pclass', hue='Survived', multiple='stack', kde=True, palette='muted')
plt.title("Histogram of Pclass with Survival Hue")
plt.xlabel("Passenger Class")
plt.ylabel("Count")
plt.show()
```
<img width="532" alt="Screenshot 2025-04-21 at 9 19 59 AM" src="https://github.com/user-attachments/assets/15255dfe-2918-4d23-95fa-2e3042408d1e" />


```
sns.boxplot(x='Pclass',y='Age',data=df,palette='rainbow')
plt.title("Age By Passenger Class")
```
<img width="458" alt="Screenshot 2025-04-21 at 9 20 07 AM" src="https://github.com/user-attachments/assets/f2514281-cffe-4c57-8690-88681499e120" />

```
sns.violinplot(x="Pclass", y="Fare", data=df)
plt.title('Violin Plot of Fare by Passenger Class')
plt.show()
```
<img width="477" alt="Screenshot 2025-04-21 at 9 20 15 AM" src="https://github.com/user-attachments/assets/366b3132-7c72-4569-923c-fe8ad5cd6b25" />

```
numeric_df = df.select_dtypes(include=['float64', 'int64'])
corr_matrix = numeric_df.corr()
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Heatmap of Titanic Dataset')
plt.show()
```
<img width="474" alt="Screenshot 2025-04-21 at 9 20 23 AM" src="https://github.com/user-attachments/assets/2d500009-dd09-4f03-88c3-09e26f759596" />

# Result:
Hence,Data Visualization using seaborn python library for the given data is implemented successfully.

```
.

















.
```
