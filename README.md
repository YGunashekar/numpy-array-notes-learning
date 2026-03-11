# my learning source for numpy
[![Watch the video](https://img.youtube.com/vi/1qz7qUM6yUI/0.jpg)](https://www.youtube.com/watch?v=1qz7qUM6yUI)

# notes typed
Python + numpy basics
Image arrays
CNN basics
TensorFlow/keras workflow
Dataset handling
Model architecture

```
started numpy

list vs numpy - 
```
numpy stores less memory than list . for example 

a=[1,2,3,4]*10000
this repeats thousand times
a=[1,2,3,4,1,2,3,4 … upto 10000times]
if we multiply with 2
that's only possible with looping each and every element with looping it multiplying to 2 .
```
lets get into coding 

lets import libraries numpy and time
```
import numpy as np
import time

now lets multiply with 2 and calculate time parllely

a=[1,2,3,4,5,6,7,8,9,10]*1000000

start =time.time()
for i in range(len(a)):
     a[i]=a[i]*2
print("\n time take for list ",time.time()-start)

output:
        time take for list 1.1340267658233643

now lets multiply same with using numpy

a=[1,2,3,4,5,6,7,8,9,10]*1000000

b=np.array(a)

start =time.time()
new_b=b*2
print("\n time take for list ",time.time()-start)

output:
        time take for list 0.03792834281921387


the reason is why numpy faster than list is they use different languages each other . numpy uses c language where list uses python . the next thing is memory .numpy stores each element in the array only as a string where as list can store them as number , float , string , etc based on the value.


lets take

a=[1,2,3,4,5]
arr=np.array(a)
print("list size:",sys.getsizeof(a))
print("array size:",arr.nbytes)

output: list size:104
        Array size:40

see another example 

a=[1,'a',"apple",2.1]
print(type(a))

output:<class 'list'>
arr=np.array()
output:
array(['1','a','apple','2.1'],dtype='<U32')

table =

feature -     speed ,  datatypes , memoryefficiency , Mathoperations , builtinfunctions
python list -  slow, mixed allowed, less efficient , manual loop,limited
numpy array -  fast(optimized in c), Samedatatype ,moreefficient ,direct(vectorized),manypowerfultools 


ok lets continue with an example

import numpy as np # where np is alias
np.array([1,2,3])
output:array([1,2,3])

lets get to dimensions and shapes

#dimensions
32 => scalar => 0 dimension
[1,2,3]=>1 dimension
[ [1,2,3][4,5,6]]=> 2 dimension

lets from this code 
arr=np.array([1,2,3])
arr
output:array([1,2,3])
arr.ndim 
output:1 #dimension of array got 1

arr=np.array(34)
arr.ndim
output:0 #dimension of array got 0

some other ways to initailze dimensions
[]=>1 dimension
[[],[]]=>2 dimension
[[[[]]]]...=> the n number of brackets increase dimensions increase from 0 to n

ok lets get into code
arr=np.array([])
arr
output:1 #dimension came 1

arr=np.array([[]])
arr
output:2 #dimension came 2

arr=np.array([[[]]])
arr
output:3 #dimension came 3

arr=np.array([[[[]]]])
arr
output:4 #dimension came 4

arr.shape
output:(1,1,1,0) # this shows and represents the four dimensional shape of an array

imagine a three dimensional box in 3d space a 4 dimensional is little complex to that

in list if we want to type the elements from 1to 10 .we type manually or use for loop . but in numpy we can give direct mathematical operations 
like in list 
for i in range(10):
    l.append[i]

in numpy we can directly np.arange(1,10) do this
for example
range = np.arange(1,10) #start and stop
range 
array([1,2,3,4,5,6,...9])

range=np.arange(1,10,2) #start and stop and step up
range
output:array([1,3,5,7,9])

arr=np.linspace(0,1,5) # start and stop and no. of values
arr
output:array([0.,0.25,0.5,0.75,1.])

arr=np.logspace(1,3,3) /* this returns the number(n) values in 10^n as start and end and number of values*/
arr
output:array([10.,100.,1000.])

lets arr=np.zeros(5)
this returns array([0.,0.,0.,0.,0.])

lets arr=np.zeros([2,3])
this returns array([0.,0.,0.],
                  [0.,0.,0.]) /* you can identify the view of row and columns here thats right vertical are columns are horizontal*/
here in np.zeros([2,3]) #2 is rows and 3 is column
where np.zeros([2,3,5,6,8]) returns a 5 dimensional array 
in this above code represents 2 blocks in each one 3 subblocks in each one 5 matrixes in each one 6 rows and 8 columns.

np.ones([4,2],dtype='int')# you can also declare the datatype in it 
returns array([[1.,1.],
               [1.,1.],
               [1.,1.],
               [1.,1.]] 
np.full([10,2]) # creates an array full of any value
returns array([2,2,2,2,2,2,2,2,2,2])


np.full([2,4],7) # creates an array full of any value
returns array([7,7,7,7],
              [7,7,7,7])

np.empty # this iniatializes an uninitialized array
np.empty([2,3]) this returns array([0.,0.,0.],
                                   [0.,0.,0.]) # this is an empty list not zeros they are empty

np.random.rand(10) this returns random floats from 0 to 1
np.random.rand([2,3]) this returns random floats from 0 to 1 by two rows and three columns 
np.random.randn() this  returns random floats from 0 to 1 in standard normal distribution 
np.random.randint(10,100) returns random interger from 1to 10 as start,stop,numer ofvalues ,output came as 99
np.random.randint(10,100,6) returns random interger from 1to 10 as start,stop,numer ofvalues ,output came as random integers from 10 to 100 by two rows and three columns .

























