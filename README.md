# About
Kohonen's Self Organizing Maps (SOM) are a form of artificial neural nets which utilize different neighborhood functions to preserve the topological properties of the input space on a `n x n` grid.

This module provides bare bones pythonic implementations of these variants. 


### Usage
##### Supervised SOM:
This implementation takes both input dataspace as well as the labels for supervised training:
```python
from selforgmap import selforgmap as som
n = 50 #to create a 50 x 50 grid
d = 3 #dimensions of input space
space = [[1.2, 3.2, 3], [2.3, 4.5, 1], [1.2, 3, 4.2]]
labels = [1, 2, 1]
obj = som.SOMSupervised(n, d)
obj.train(space, labels)
obj.predict([1.1, 2.1, 3.2])
```


####### Author: saifuddin778