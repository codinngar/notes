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
df.skew()
df["two"].mean()

# make a data frame from a loop
data = [{"i^2": i**2, "i^3": i**3} for i in range(10)]
df = pd.DataFrame(data)

# make a data frame from dictionaries and fill empty with NaN
df = pd.DataFrame({"one": 1, "two": 2}, {"one": 3, "two": 4})
df = pd.DataFrame({"one": 1, "two": 2}, {"three": 3, "four": 4})
```