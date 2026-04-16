# PANDAS_Exercises
PANDAS library exploration and exercise repo

Here I will explore the PANDAS library commonly used for Data Analysis. 
First things first - installation.
Since i have Python installed in my machine, process is straight forward: running a simple line of command in either `CMD` (windows machine) or editor terminal (I'm using VSCode)
```
python -m pip install pandas
```
Just restart your editor after the command is executed and voila! Everything should work just fine!

For more information on PANDAS and its codebase can be found below:
- [Codebase in Github](https://github.com/pandas-dev/pandas)
- [Introduction and explanation by W3 Schools](https://www.w3schools.com/python/pandas/default.asp)

Now that we have it installed, lets go and start exploring the capabilities of PANDAS!
____

For the basic exercises I will be using a tiny dataset from Kagle just to understand the basic functions, later on i will perform the exercises with larger and more complex datasets.
Practice dataset used can be found [here](https://www.kaggle.com/datasets/themrityunjaypathak/pandas-practice-dataset).
For the reason of checking and analysing the result of each action I'm making I will be adding `print()` where necessary.

## Working with the dataset

- Reading the CSV file:
```PYTHON
import pandas as pd

df = pd.read_csv(r'C:\Users\username\datasets\data.csv')
print(df)
```

This returns the dataset in the terminal, since I'm working with a considerably small set (33 rows), adding a `set_option` to view the whole set is reasonable

```PYTHON
pd.set_option('display.max_rows', None)
```
`set_option` persists only within the same Python session.

Returned result:

<img width="389" height="563" alt="image" src="https://github.com/user-attachments/assets/60267ebb-5360-454f-9209-91dff25b3027" />

### Cleaning the data
- Dealing with empty cells or cells with `NULL` values by deleting the rows:
Clean the data in current DataFrame without creating a new one. To do that I'm using `dropna()` method with `inplace = True` argument.
```PYTHON
import pandas as pd

df = pd.read_csv(r'C:\Users\username\datasets\data.csv')
df.dropna(inplace = True)
print(df)
```
Alternatively a new DataFrame could be created when cleaning data. For that using `dropna()` *without* the `inplace = True` argument
```PYTHON
import pandas as pd

df = pd.read_csv(r'C:\Users\username\datasets\data.csv')
clean_df = df.dropna()
print(clean_df)
```
Result after removing `NULL` values / empty cells:

<img width="387" height="512" alt="image" src="https://github.com/user-attachments/assets/6e7b4c41-72dc-4d2b-b26e-775fa5c3e9a0" />

Alternative for deleting empty the empty cells is filling them with data. For that The `fillna()` method allows me to replace empty cells with a value:

```PYTHON
import pandas as pd

df = pd.read_csv(r'C:\Users\username\datasets\data.csv')
df.fillna(100, inplace = True)
print(df)
```

> WORK IN PROGRESS...
