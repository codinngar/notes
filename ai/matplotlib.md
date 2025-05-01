```python
import matplotlib.pyplot as plt

# use a style for plots
plt.style.use("bmh")

# make axis equal
plt.axis("equal")

# plot x and y lists by lines
plt.plot(x, y, <options>)
# marker="o"
# linestyle="dashed"
# linewidth=10
# "g--" -> set color green and line style dashed
# "-o" -> set marker for points and line style solid

# set graph title
plt.title("title")

# set labels for x and y
plt.xlabel("x")
plt.ylabel("y")

# plot two graphs with the same x
plt.plot(x, y1, x, y2, x, y3)

# plot graph with error value
plt.errorbar(x, y, <options>)
# yerr=dy
# xerr=dy
# fmt="o"
# color="b"
# ecolor="r"
# capsize=4
# elinewidth=2

# plot x and y lists with points
plt.scatter(x, y, <options>)
# c="b" -> color
# s=30 -> size
# alpha -> opacity

# plot x as a pie with lables of y
plt.pie(x, <options>)
# labels=["one", "two"] -> set lables for data
# explode=[0.1, 0.8...] -> make spaces between slices
# autopct="%1.1f%%" -> content of slices
# shadow=True
# startangle=90
# labeldistance=1.5
# pctdistance=1.3
```