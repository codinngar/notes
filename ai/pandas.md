```python
import pandas as pd

# make a series of data like a table
data = pd.Series([0.25, 0.5, 0.75, 1])

# return series values, index and keys
data.values
data.index
data.keys

# make a description about the series
data.describe()

# show needed data only
data.agg(["mean", "sum"])

# make your own index
pd.Series([1, 2, 3], index=["a", "b", "c"])
pd.Series({"a": 1, "b": 2, "c": 3})

# access elements in series
data[1]
data["a"]

# make a list
x1 = pd.Index([1, 6, 7, 4, 9])
x2 = pd.Index([1, 8, 9, 3, 7])

# logical operators
x1 & x2 # and
x1 | x2 # or
x1 ^ x2 # xor

# plot data with x is the index and y is the data
data.plot(kind="line")

# make a table from data
array = np.array([[32, 76, 29], [26, 68, 34], [76, 45, 96]])
x = ["a", "b", "c"]
y = ["one", "two", "three"]
df = pd.DataFrame(array, index=x, columns=y)

# the same output as the above
x = pd.Series({"a": 32, "b": 26, "c":76})
y = pd.Series({"a": 76, "b": 68, "c":45})
z = pd.Series({"a": 29, "b": 34, "c":96})
df = pd.DataFrame({"one": x, "two": y, "three": z})

# return column data
df["one"]

# transpose table
df.T

# return tables keys and values
df.keys()
df.values

# reshape data like a stack
df.stack()

# return specific rows and columns from data table
df.iloc[:3, :2]

# return specific rows and columns from data table
df.loc["a":"c", "two":]

# return the rows that satisfies the condition
df.loc[df.one > 3]

# return specific columns and rows based on condition
df.loc[df.one > 3, ["one", "three"]]

# return columns and index
df.columns
df.index

# sort values of a column
df.sort_values(["one"], ascending=True)

# return specific data from data frame
df.min()
df.max()
df.std()
df.corr()
df.prod()
df.skew()
df.count()
df["two"].mean()
df.sum(axis="columns")

# make a data frame from a loop
data = [{"i^2": i**2, "i^3": i**3} for i in range(10)]
df = pd.DataFrame(data)

# make a data frame from dictionaries and fill empty with NaN
df = pd.DataFrame({"one": 1, "two": 2}, {"one": 3, "two": 4})
df = pd.DataFrame({"one": 1, "two": 2}, {"three": 3, "four": 4})

# make a new column with a value of the sum of all
df["total"] = df["one"] + df["two"] + df["three"]

# make a table it's values is the summaition of data
pd.eval("df.one + df.two + df.three")

# return the data that satisfies the conditions
df.query("one > 3 and three < 5")

# return the data that satisfies the conditions
condition = (df.one > 3) & (df.three < 5)
df[condition]

# make a data frame from a function
def make_df(cols, index):
    data = {c: [c + str(i) for i in index] for c in cols}
    return pd.DataFrame(data, index)

df = make_df("ABC", range(3))

# merge two data frames with common columns then delete name column
df1 = pd.DataFrame({'employee': ['Bob', 'Jake', 'Lisa', 'Sue'],
                    'group': ['Accounting', 'Engineering', 
                              'Engineering', 'HR']})

df2 = pd.DataFrame({'name': ['Bob', 'Jake', 'Lisa', 'Sue'],
                    'salary': [70000, 80000, 120000, 90000]})

pd.merge(df1, df2, left_on="employee", right_on="name").drop("name", axis=1)

# set employee column as the index
df.set_index("employee")

# normal merge
pd.merge(df1, df2, how="outer")

# return the intersection between two data frames
pd.merge(df1, df2)
pd.merge(df1, df2, how="inner")

# retrun the second data frame complete and merge with it df1
pd.merge(df1, df2, how="right")

# groub the same keys with each others and sum their values
df.groupby("key").sum()

# groub by key and take the min of data1 and if they equal take the max of data2
df = pd.DataFrame({'key': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'data1': range(6),
                   'data2': np.random.randint(0, 10, 6)},
                    columns = ['key', 'data1', 'data2'])

df.groupby('key').aggregate({'data1': 'min','data2': 'max'})

# groub by key then filter the output
def filter_func(x):
    return x['data2'].std() > 4

df.groupby('key').filter(filter_func)

# groub by key then transform each data from x to x^2
df.groupby('key').transform(lambda x: x**2)

# make a multi index table
index = [('California', 2000),('California', 2010),
         ('New York', 2000),('New York', 2010),
         ('Texas', 2000),('Texas', 2010)]

populations = [10000,15000,
               20000,25000,
               30000,35000]

index = pd.MultiIndex.from_tuples(index)
pop = pd.Series(populations, index=index)

# make rows columns and columns 
pop.unstack()

# make a multi index table from a data frame
df = pd.DataFrame(np.random.random((4, 2)), [["a", "a", "b", "b"], [1, 2, 1, 2]], ["one", "two"])

# make a multi index table from a series
data = {('California', 2000): 10000,('California', 2010):15000,
        ('Texas', 2000): 20000,('Texas', 2010): 25000,
        ('New York', 2000): 30000,('New York', 2010): 35000}

df = pd.Series(data)

# make a multi index table
index = pd.MultiIndex.from_product([[2010, 2011], [1, 2]], names=["year", "month"])
columns = pd.MultiIndex.from_product([["BMW", "Ferrari", "Maserati"], ["Gas", "Petrol"]], names=["Car", "Fuel"])
data = np.random.randint(30, 100, (4, 6))
df = pd.DataFrame(data, index, columns)

# return a specific data from a multiindex table
df.loc[:, ("BMW", "Petrol")]

# return a specific data from a multiindex table
idx = pd.IndexSlice
print(df.loc[idx[:, 1], idx[:, 'HR']])

# string handling
pd.Series(data).str.len()

# date handling
date = pd.to_datetime("4th of July, 2020")

# add days to the current date
new_date = date + pd.to_timedelta(np.arange(20), "D")

# get days between two dates
pd.date_range("2023-06-12", "2024-12-04")

# get the next dates with frequency of 2 hours, 30 minutes and 10 seconds
pd.date_range("2023-06-12", periods=8, freq="2H30T10S")

# get the next dates with frequency of business days
pd.date_range("2023-06-12", periods=8, freq=BDay())

# read csv file and make col as index
file = pd.read_csv("file.csv", index_col="col")

# read first 30 lines
file.head(30)

# save data as a csv file and set names for columns
data.to_csv("file.csv", names=["one", "two"])

# save data as an excel file
data.to_excel("file.xlsx", sheet_name="Sheet 1")

# set options for output
pd.set_option("display.width", 1000)
```