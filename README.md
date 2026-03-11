# my learning source for numpy
[![Watch the video](https://img.youtube.com/vi/1qz7qUM6yUI/0.jpg)](https://www.youtube.com/watch?v=1qz7qUM6yUI)

# notes typed
Python + NumPy Basics
Topics Covered

Python + NumPy basics

Image arrays

CNN basics

TensorFlow / Keras workflow

Dataset handling

Model architecture

Currently learning NumPy basics.

List vs NumPy

NumPy uses less memory and is much faster than Python lists.

Example
a = [1,2,3,4] * 10000

This repeats the list:

[1,2,3,4,1,2,3,4 ... repeated 10000 times]

If we want to multiply each element by 2, in a list we must use a loop.

List Performance Example
import numpy as np
import time

a = [1,2,3,4,5,6,7,8,9,10] * 1000000

start = time.time()

for i in range(len(a)):
    a[i] = a[i] * 2

print("Time taken for list:", time.time() - start)
Output
Time taken for list: 1.1340267658233643
NumPy Performance Example
import numpy as np
import time

a = [1,2,3,4,5,6,7,8,9,10] * 1000000
b = np.array(a)

start = time.time()

new_b = b * 2

print("Time taken for NumPy:", time.time() - start)
Output
Time taken for NumPy: 0.03792834281921387
Why NumPy is Faster

NumPy is implemented in C

Uses vectorized operations

Uses continuous memory storage

Memory Comparison
import numpy as np
import sys

a = [1,2,3,4,5]
arr = np.array(a)

print("List size:", sys.getsizeof(a))
print("Array size:", arr.nbytes)
Output
List size: 104
Array size: 40
Data Types
Python List
a = [1, 'a', "apple", 2.1]
print(type(a))

Output

<class 'list'>

Lists allow mixed datatypes.

NumPy Array
import numpy as np

a = [1,'a',"apple",2.1]
arr = np.array(a)
print(arr)

Output

array(['1','a','apple','2.1'], dtype='<U32')

NumPy converts everything into one datatype.

Comparison Table
Feature	Python List	NumPy Array
Speed	Slow	Fast (optimized in C)
Data types	Mixed allowed	Same datatype
Memory	Less efficient	More efficient
Math operations	Manual loop	Direct vectorized
Built-in functions	Limited	Many powerful tools
Creating NumPy Arrays
import numpy as np

np.array([1,2,3])

Output

array([1,2,3])
Dimensions
Example	Meaning	Dimension
32	Scalar	0D
[1,2,3]	Vector	1D
[[1,2,3],[4,5,6]]	Matrix	2D
Example
arr = np.array([1,2,3])
arr.ndim

Output

1
Dimension Examples
arr = np.array(34)
arr.ndim

Output

0

Increasing brackets increases dimensions.

[] → 1D
[[]] → 2D
[[[]]] → 3D
[[[[]]]] → 4D
Example
arr = np.array([[[[]]]])
arr.ndim

Output

4
Shape
arr.shape

Output

(1,1,1,0)
Creating Number Sequences
arange()
np.arange(1,10)

Output

array([1,2,3,4,5,6,7,8,9])

Step example:

np.arange(1,10,2)

Output

array([1,3,5,7,9])
linspace()
np.linspace(0,1,5)

Output

array([0.,0.25,0.5,0.75,1.])
logspace()
np.logspace(1,3,3)

Output

array([10.,100.,1000.])
Arrays with Zeros
np.zeros(5)

Output

array([0.,0.,0.,0.,0.])
2D Zeros
np.zeros([2,3])

Output

[[0. 0. 0.]
 [0. 0. 0.]]

Here:

2 → rows

3 → columns

Higher Dimensions
np.zeros([2,3,5,6,8])

This creates a 5D array:

2 blocks
3 sub-blocks
5 matrices
6 rows
8 columns
Arrays with Ones
np.ones([4,2], dtype='int')

Output

[[1 1]
 [1 1]
 [1 1]
 [1 1]]
Full Arrays
np.full([2,4],7)

Output

[[7 7 7 7]
 [7 7 7 7]]
Empty Arrays
np.empty([2,3])

Creates an uninitialized array (values depend on memory).

Random Arrays
Random floats
np.random.rand(10)

Random numbers between 0 and 1.

Random matrix
np.random.rand(2,3)
Normal distribution
np.random.randn(5)
Random integers
np.random.randint(10,100)

Single integer between 10 and 100.

np.random.randint(10,100,6)

6 random integers between 10 and 100.












