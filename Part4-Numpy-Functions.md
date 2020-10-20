# NumPy Functions
## Numpy Array Shape:
`ndarray.shape` will display a tuple of integers that indicate the number of elements stored along each dimension of the array. If, for example, you have a 2-D array with 2 rows and 3 columns, the shape of your array is (2, 3).
```python
   import numpy as np
   arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
   arr1= np.array([1,2,3,4])

   print(arr.shape)
   print(arr1.shape)
 ```
**Result:**
```python
   (2, 4)
   (4,)
 ```
 **All In One Example**
```python
   array_example = np.array([[[0, 1, 2, 3],
                            [4, 5, 6, 7]],

                           [[0, 1, 2, 3],
                            [4, 5, 6, 7]],

                           [[0 ,1 ,2, 3],
                            [4, 5, 6, 7]]])
 
   print('No of dimensions of the array:',array_example.ndim)     # .ndim for dimensions
   print('Total no of elements of the array:',array_example.size) # .size for size
   print('Shape of the array:',array_example.shape)                # .shape for shape
 ```
 **Result:**
 ```python
    No of dimensions of the array: 3
    Total no of elements of the array: 24
    Shape of the array: (3, 2, 4)
 ```
 ### After knowing the shape of an Array you would be feeling like to reshape it... But can you??
 ### Yes You can Absolutely...
 ## NumPy Array Reshaping
 Using `arr.reshape()` will give a new shape to an array without changing the data.
 
 Just remember that when you use the reshape method, the array you want to produce needs to have the same number of elements as the original array.
 **Reshape from 1-D to 2-D**
```python
   import numpy as np
   arr1 = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])
   newarr1 = arr1.reshape(4, 3)
   arr2 = np.array(['D','e','V','I','n','c','e','p','t'])
   newarr2 = arr2.reshape(3,3)
   print(newarr1)
   print(newarr2)
 ```
 **Result:**
 ```python
    [[ 1  2  3]
     [ 4  5  6]
     [ 7  8  9]
     [10 11 12]]
    
    [['D' 'e' 'V']
     ['I' 'n' 'c']
     ['e' 'p' 't']]
 ```
 **Reshape from 1-D to 3-D**
 ```python
    import numpy as np
    arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])
    newarr = arr.reshape(2, 3, 2)
    print(newarr)
  ```
 **Result:**
 ```python
    [[[ 1  2]
      [ 3  4]
      [ 5  6]]

     [[ 7  8]
      [ 9 10]
      [11 12]]]
 ```
 ### Can we Reshape into any Shape??
 Yes, as long as the elements required for reshaping are equal in both shapes.
 
 **We can reshape an 8 elements 1D array into 4 elements in 2 rows 2D array but we cannot reshape it into a 3 elements 3 rows 2D array as that would require 3x3 = 9 elements.**
 
 * We can use `reshape(-1)` to convert mult-dimensional array into 1-D array.  
```python
   import numpy as np
   arr = np.array([[1, 2, 3], [4, 5, 6]])
   newarr = arr.reshape(-1)
   print(newarr)
```
**Result:**
```python
   [1 2 3 4 5 6]
 ```
 
# NumPy Sorting and Searching
## NumPy Sorting
* Sorting means putting elements in an ***ordered sequence.***
* The NumPy ndarray object has a function called `sort()`, that will sort a specified array.
```python
   import numpy as np
   arr1 = np.array([3, 2, 0, 1])
   arr2 = np.array(['red','blue','green'])
   
   # 2-D array
   arr3 = np.array([[3, 2, 4], [5, 0, 1]])
   
   print(np.sort(arr1))
   print(np.sort(arr2))
   print(np.sort(arr3))
```
**Result:**
```python
   [0 1 2 3]
   ['blue' 'green' 'red']
   [[2 3 4]
    [0 1 5]]
```
## NumPy Searching
Searching is an operation or a technique that helps finds the place of a given element or value in the list. Any search is said to be successful or unsuccessful depending upon whether the element that is being searched is found or not.

### 1. where() : 
Returns the indices of the searched value.
```python
   import numpy as np
   arr1 = np.array([1, 2, 3, 4, 5, 4, 4])
   x = np.where(arr1 == 4)
   y = np.where(arr1%2 == 0)
   z = np.where(arr1%2 == 1)
   print(x)
   print(y)
   print(z)
```
**Result:**
```python
   (array([3, 5, 6]),) # Which means that the value 4 is present at index 3, 5, and 6.
   (array([1, 3, 5, 6]),)
   (array([0, 2, 4]),)
 ```
### 2. searchsorted() :
Performs a binary search in the array, and returns the index where the specified value would be inserted to maintain the search order.
> The **searchsorted()** method is assumed to be used on sorted arrays.
```python
   import numpy as np
   arr1 = np.array([6, 7, 8, 9])
   x = np.searchsorted(arr1, 7)
   print(x)
   
   # Multiple values
   arr2 = np.array([1, 3, 5, 7])
   y = np.searchsorted(arr2, [2, 4, 6])
   print(y)
```
**Result:**
```python
   1
   
   [1 2 3]
```
**For more advanced sorting and searching example you can follow the link here ---->>** [Advanced Sorting And Searching](https://www.geeksforgeeks.org/numpy-sorting-searching-and-counting/)    
   

## Mean, Median, Mode
Yes these are the topics you must have studied in High school...You must be wondering what their use.??

To say they are very important and **NumPy** also have functions for them. You can use these function on large data sets and find the answers in just seconds..:smile:

### Mean
* **Mean** - The average value
* To calculate the mean, find the sum of all values, and divide the sum by the number of values.

**As you all know Python makes everything easy see it yourself.**
```python
   import numpy as np
   arr=np.array([19,13,18,21,44,17,12,31,37,8,12,27])
   x=np.mean(arr)
   print(x)
 ```
 **Result:**
 ```python
    21.5833333333
 ```
### Median
* **Median** - The mid point value
* The median value is the value in the middle, after you have sorted all the values.
```python
   import numpy
   # For one value in the middle
   speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]
   x = numpy.median(speed)
   print(x)
   
   # For two values in the middle
   speed1 = [99,86,87,88,86,103,87,94,78,77,85,86]
   y = numpy.median(speed1)
   print(y)
```
**Result:**
```python
   87.0
   
   86.5
```

### Mode
* **Mode** - The most common value
* The Mode value is the value that appears the most number of times.

> This function comes under **SciPy**
```python
   from scipy import stats
   speed = [99,86,87,88,111,86,103,87,94,78,77,85,86]
   x = stats.mode(speed)
   print(x)
 ```
**Result:**
```python
   ModeResult(mode=array([86]), count=array([3]))

   ##The mode() method returns a ModeResult object that contains the mode number (86), and count (how many times the mode number appeared (3)).
```

## Standard Deviation (σ)
* Standard deviation is a number that describes how spread out the values are.
* A low standard deviation means that most of the numbers are close to the mean (average) value.
* A high standard deviation means that the values are spread out over a wider range.
> Use the NumPy **std()** method to find the standard deviation:
   
```python
   import numpy
   speed = [86,87,88,86,87,85,86]
   x = numpy.std(speed)
   print(x)
   
   speed1 = [32,111,138,28,59,77,97]
   y = numpy.std(speed1)
   print(y)
```
**Result:**
```python
   0.9035079029052513
   
   37.84501153334721
```

