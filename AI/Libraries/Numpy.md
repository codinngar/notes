```python
import numpy as np

# make a matrix from a list
a = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
np.array(a)

# make three random numbers from 1 to 10
np.random.uniform(1, 10, 3)

# make a matrix of random numbers with size of 2x3
np.random.random((2, 3))
np.random.rand(2, 3)

# make an empty array with size of 4x3
np.empty((4, 3))

# make a matrix with size 1x3 with random values from 1 to 9
np.random.randint(1, 10, 3)

# make a matrix with size of 3x2 with random values from 0 to 9
np.random.randint(0, 10, (3, 2))

# reshape matrix a to 3x3 matrix
np.reshape(a, (3, 3))

# create an array with a structured data type
np.array(
    [("x", 1, 3.5), ("y", 2, 6.5), ("z", 3, 9.5)],
    dtype=[("name", "U3"), ("number", "i1"), ("value", "f2")],
)

# choose a random value from given values
np.random.choice([1, 2, 3, 4])

# randomize values of a
np.random.shuffle(a)

# make a matrix of zeros or ones of size 1x3
np.zeros(3)
np.ones(3)

# make an identity matrix of size 5x5
np.eye(5)

# make a matrix of size 2x3 and fill it all with 8
np.full((2, 3), 8)

# make a matrix of size 8 with values from 0 to 7
np.arange(8)

# make a matrix of 5 values from 0 to 20 ([0 5 10 15 20])
np.linspace(0, 20, 5)

# make a diagonal matrix from the given matrix with a padding of 5
np.diag(array([1, 2, 3]), 5)

# return the count of non zero values and larger than 3 in every row
np.count_nonzero(a > 3, axis=1)

# return True if there is at least one element in matrix a is larger than 5
np.any(a > 5)

# return True if there all elements in matrix a is larger than 5
np.all(a > 5)

# make matrix c with values of a that is larger than 3
b = a > 3
c = a[b]

# check every element in two matrices if they are close of each other with 0.3
np.isclose(a, b, 0.3)

# make b matrix with values of a * 5
np.multiply(a, 5, b)

# make b matrix with values of a ^ 2
np.power(a, 2, b)

# return the sum of all matrix elements
np.add.reduce(a)
```