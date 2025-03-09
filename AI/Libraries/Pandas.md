
```python
import pandas as pd

# make a series of data like a table
a = pd.Series([0.25, 0.5, 0.75, 1])

# return series values, index and keys
a.values
a.index
a.keys

# make a description about the series
a.describe()

# show needed data only
a.agg(["mean", "sum"])

# make your own index
pd.Series([1, 2, 3], index=["a", "b", "c"])
pd.Series({"a": 1, "b": 2, "c": 3})

# access elements in series
a[1]
a["a"]

# make a list
x1 = pd.Index([1, 6, 7, 4, 9])
x2 = pd.Index([1, 8, 9, 3, 7])

# logical operators
x1 & x2 # and
x1 | x2 # or
x1 ^ x2 # xor
```