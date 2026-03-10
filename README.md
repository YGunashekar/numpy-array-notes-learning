# my learning source for numpy
[![Watch the video](https://img.youtube.com/vi/1qz7qUM6yUI/0.jpg)](https://www.youtube.com/watch?v=1qz7qUM6yUI)

# notes typed
Python + numpy basics
Image arrays
CNN basics
TensorFlow/keras workflow
Dataset handling
Model architecture


started numpy

list vs numpy - 

numpy stores less memory than list . for example 

a=[1,2,3,4]*10000
this repeats thousand times
a=[1,2,3,4,1,2,3,4 … upto 10000times]
if we multiply with 2
that's only possible with looping each and every element with looping it multiplying to 2 .

lets get into coding 

lets import libraries numpy and time

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





