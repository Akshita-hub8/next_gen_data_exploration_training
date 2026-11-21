# Day 01 – Python Fundamentals and Data Analytics

## Topics Covered

- Introduction to data and importance of data types
- Python data types: integer, float, string, and boolean
- Python data structures: lists, tuples, dictionaries, and sets
- Practice using conditional statements and functions
- Pandas Series and DataFrames
- Data pipeline: importing, understanding, cleaning, transforming, analyzing, visualizing data, and deriving insights

## Practice Questions and Code

```python
# Integer (int) - Used for whole numbers.
age = 21
students = 50

print(age)
print(type(age))
```

```python
# Float - Use for decimal values
salary = 55000.75

print(salary)
print(type(salary))
```

```python
# String (str) - stores text
name = "123"

print(name)
print(type(name))
```

```python
# Boolean (bool)- use for true or false
is_placed = True

print(is_placed)
print(type(is_placed))
```

```python
marks = [78, 85, 90, 67, 88]

print(marks)
print(type(marks))
```

```python
sales = [1200, 1500, 1800, 2200]

print(max(sales))
print(min(sales))
print(sum(sales))
```

```python
months = ("Jan", "Feb", "Mar")

print(months)
print(type(months))
```

```python
user = {"name": "Alex", "role": "Developer"}

print(user)
print(type(user))
```

```python
student = {
    "Name": "Aman",
    "Age": 21,
    "CGPA": 8.4
}

print(student)
print(student["CGPA"])
```

```python
unique_ids = {101, 102, 103, 101}
print(unique_ids)
print(type(unique_ids))
```

```python
cities = {"Delhi", "Mumbai", "Delhi", "Pune"}

print(cities)
```

### Practice Question 1                                          
A student will not be allowed to sit in exam if his/her attendance is less than 75%.
Take following input from user
Number of classes held
Number of classes attended.
And print
percentage of class attended
Is student is allowed to sit in exam or not.

```python
print("Enter the data")
total_class=int(input("Number of classes held: "))
attended_class=int(input("Number of classes attended: "))
percentage=(attended_class/total_class)*100
print("\n Outcome")
if percentage >= 75:
      print("Percenatge of Class attended: ", percentage)
    print("Student is allowed to sit in exam")
else:
    print("Percenatge of class attended: ", percentage)
    print("Student is not allowed to sit in exam")
```

### Practice Question 2                      
Enter the input a character from user and check whether the given character is alphabet or not.

### Practice Question 2                      
Enter the input a character from user and check whether the given character is alphabet or not.

```python
a=input("Please enter the character: ")
if(a.isupper() or a.islower()):
	print(a," is a alphabet")
else:
	print(a, "is not a alphabet")
```

### Practice Question 3                                                    Write a Python function that takes a list and returns a new list with unique elements of the first list.

```python
def unique_list(l):
  x = []
  for a in l:
    if a not in x:
      x.append(a)
  return x
list1=[1,2,3,3,3,3,4,5]
print(unique_list(list1))
```

### Practice Question 4:                                                    Make a two-player Rock-Paper-Scissors game.

```python

c=True
while(c!='False'):
    n1=input("Enter the first player name: ")
    n2=input("Enter the second player name: ")
    print("\n")
    opt1=input("Enter rock/paper/scisor for player 1: ")
    opt2=input("Enter rock/paper/scisor for player 2: ")
    print("\n Output")
    if((opt1=='scisor' and opt2=='paper') or (opt1=='paper' and opt2=='scisor')):
        print("Scisor Wins")
    elif((opt1=='stone' and opt2=='scisor') or (opt1=='scisor' and opt2=='stone')):
        print("Stone Wins")
    elif((opt1=='stone' and opt2=='paper') or (opt1=='paper' and opt2=='stone')):
        print("Paper Wins")
    elif(opt1==opt2):
        print("Match Draw")
    else:
        print("You have chosen the wrong input")

    c=input("Do you want to restart enter True else False: ")
    print(c)
```

### Practice Question 5 Write a Python program to find the items that start with a specific character from a given list

```python
a=int(input("How many strings you want to enter: "))
list=[]
for i in range(0,a):
	i=input()
	list.append(i)
print(list)

counter=0
for i in list:
	if(i[0]=='a'):
		counter=counter+1
print("The number of strings is: ",counter)
```

### Practice Question 6 Write a Python program to interleave two given lists into another list randomly

```python
import random
list1=['a','b','c']
list2=[1,2,3]
list3=[]
a=len(list1)
b=len(list2)
c=a+b
i=0
for i in range(0,c):
    i=random.sample(list1+list2,1)
    list3.append(i)

print(list3)
```

### Practice Question 7 Write a Python program to add a key to the dictionary

```python
s={1:"a",2:"b"}
print("Initial Dictionary is: ")
print(s)
print("\n")
print("Dictionary after addition of key is: ")
s.update({3:"c"})
print(s)
```

### Practice Question 8 Write a python program to concatenate two dictionaries and create a new one

```python
s={1:"a",2:"b"}
s1={3:"c",4:"d"}
print("\n")
print("First Dictionary is: ")
print(s)
print("\n")
print("Second Dictionary is: ")
print(s1)
s3={}
for i in (s,s1):
	s3.update(i)
print("\n")
print("After concatenation of first and second: ")
print(s3)
```

### Practice Question 9 Write a program to check whether a given key already exists in a dictionary

```python
s={1:"a",2:"b",3:"c",4:"d"}
key=int(input("Enter the key you want to check: "))
if key in s:
	print("Key already exists")
else:
	print("Key does not exist")
```

### Practice Question 10: Write a Python function that takes two lists and returns True if they have at least one common member

### Practice Question 10: Write a Python function that takes two lists and returns True if they have at least one common member

```python
list1=['red','green','white','black','pink','yellow']
list2=['a','b','c','d','red']

print("List 1: ")
print(list1)
print("\nList 2: ")
print(list2)
def fun(l1,l2):
    result=False
    for i in l1:
        for j in l2:
            if i==j:
                result=True
    return result

print("\nOutput")
print(fun(list1,list2))
```

### Practice Question 11 Program to find no. Of repeated items in the tuple

```python
t1=('a','b','c','a','b','d')
print("\n Tuple is: ")
print(t1)
words=''.join(t1)
l=dict()
for i in words:
	if i not in l:
		l[i]=1
	else:
		l[i]=l[i]+1
print("\n Repeated Items in the tuple are: ")
print(l)
```

### Practice Question 12 Program to replace the last value of tuples in the list

```python
t=[(1,2),(3,4),(5,6),(7,8),(9,10)]
print("\nOriginal List is: ")
print(t)
t2=[]
for i in t:
	t2.append([i[:-1] + (100,)])
print("\nList after replacement of last element of tuple with 100 is: ")
print(t2)
```

```python
# Pandas Series
# Series = Single column of data.
import pandas as pd

ages = pd.Series([21,22,23,24])

print(ages)
```

```python
# Pandas Dataframes
# A DataFrame is similar to an Excel sheet.

import pandas as pd

data = {
    "Name":["Aman","Riya","Simran"],
    "Age":[21,22,20],
    "Marks":[85,92,88]
}

df = pd.DataFrame(data)

print(df)
```

```python
print(df.dtypes)
```

```python
# import libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

```python
# Load Dataset

from google.colab import drive
drive.mount('/content/drive')

import pandas as pd

df = pd.read_csv("/content/drive/MyDrive/student1.csv")
```

```python
df.head()
```

```python
# Understand the Dataset
df.shape
```

```python
df.columns
```

```python
df.dtypes
```

```python
df.info()
```

```python
# Data Cleaning
# Missing Value
print(data.dtypes)
```

```python
# Fill missing value
df["Age"] = df["Age"].fillna(df["Age"].mean())
df["Attendance"] = df["Attendance"].fillna(df["Attendance"].mean())
df.head()
```

```python
df.duplicated()
```

```python
df = df.drop_duplicates()
```

```python
df["Gender"] = df["Gender"].str.title()
```

```python
df
```

```python
# Add new column "Performance Grade"

def grade(cgpa):
    if cgpa >= 9:
        return "Excellent"
    elif cgpa >=8:
        return "Good"
    elif cgpa >=7:
        return "Average"
    else:
        return "Poor"

df["Grade"] = df["CGPA"].apply(grade)
```

```python
df.head()
```

```python
# Creating attendance status
df["Attendance_Status"] = df["Attendance"].apply(
    lambda x: "Regular" if x>=75 else "Irregular"
)
```

```python
df.head()
```

```python
# Basic Data analysis
print(df["CGPA"].mean())
print(df["Attendance"].max())
df["Placement_Status"].value_counts()
```

```python
#Basic Data analysisprint(df["CGPA"].mean())
print(df["Attendance"].max())
df["Placement_Status"].value_counts()
```

```python
sns.boxplot(y=df["Attendance"])

plt.title("Attendance Boxplot")
plt.show()
```

```python
sns.countplot(data=df,x="Department")

plt.title("Students by Department")

plt.show()
```

```python
sns.scatterplot(
    data=df,
    x="Attendance",
    y="CGPA",
    hue="Placement_Status"
)

plt.show()
```

```python
plt.figure(figsize=(6,4))

sns.heatmap(
    df.select_dtypes(include="number").corr(),
    annot=True,
    cmap="coolwarm"
)

plt.show()
```

## Key Learnings

- Understood Python’s basic data types and how to identify them using `type()`.
- Practiced using lists, tuples, dictionaries, and sets to store and work with collections of data.
- Applied Python logic to solve beginner programming exercises.
- Learned the basics of Pandas Series and DataFrames.
- Introduced the data analytics workflow, including dataset inspection, cleaning, transformation, analysis, and visualization.

