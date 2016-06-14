# About
Kohonen's Self Organizing Maps (SOM) are a form of artificial neural nets which utilize different neighborhood functions to preserve the topological properties of the input space on a `n x n` grid.

This module provides bare bones pythonic implementations of these variants. 


### Installation
Install using `pip install -U selforgmap`

### Usage

##### Generic SOM:
This implementation takes just input dataspace for unsupervised training:
```python
from selforgmap.selforgmap import SOM
n = 10 #to create a 10 x 10 grid
d = 3 #dimensions of input space
space = [[1.2, 3.2, 3], [2.3, 4.5, 1], [1.2, 3, 4.2]]
obj = SOM(n, d)
obj.train(space)
nodes = obj.get_nodes() #all the trained nodes
bmus = obj.get_bmus() #just the nodes which are marked as closest to the input space
```

The structure of each element in the retreived `nodes` and `bmus` contains respective `x`, `y`, `weights` and `hcount` parameters, indicating x-axis coordinate, y-axis coordinate, numerical weights and the number of times the node has been hit (`hcount`) as a best matching unit (or bmu).


##### Supervised SOM:
This implementation takes both input dataspace as well as the labels for supervised training:
```python
from selforgmap.selforgmap import SOMSupervised
n = 50 #to create a 50 x 50 grid
d = 3 #dimensions of input space
space = [[1.2, 3.2, 3], [2.3, 4.5, 1], [1.2, 3, 4.2]]
labels = [1, 2, 1]
obj = SOMSupervised(n, d)
obj.train(space, labels)
prediction = obj.predict([1.1, 2.1, 3.2])
```

Note: The supervised version also supports the retreival of `nodes` and `bmus` for further analysis. 


####### Author: saifuddin778
