# NumPy Basics

Context:

* What is NumPy?
* Why Use NumPy?
* Creating Arrays Using NumPy
* NumPy Array:
   * Indexing
   * Slicing
   * NumPy Data Types
   * NumPy COPY vs View
   * Shape vs Reshape
   * Iteration
   * Join
   * Split
   * Search
   * Sort & Filter

* NumPy Random:
   * Random Intro
   * Data Distribution
   * Random Permutations
   * Seaborn Module
   * Normal Distribution
   * Binomial Distribution
   * Poisson Distribution
   * Uniform Distribution
   * Logistic Distribution
   * Multinomial Distribution
   * Exponential Distribution
   * Chi Square Distribution
   * Rayleigh Distribution
   * Pareto Distribution
   * Zipf Distribution
  

## **What is NumPy?**

**NumPy (Numerical Python) is a powerful library for:**

* Working with arrays (especially multidimensional arrays).
* Performing fast mathematical operations.
* Supporting tools for linear algebra, Fourier transforms, random numbers, etc. It provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays.
* The core of the library is the ndarray object, which is a fast and memory-efficient way to handle numerical data.
* NumPy aims to provide an array object that is up to 50x faster than traditional Python lists.


**Import NumPy:**

Once NumPy is installed, import it in your applications by adding the import keyword:
```
import numpy
```

**Example:**
```
import numpy

arry = numpy.array([1,2,3,4,5])

print(arry)
print(type(arry))
```
**Output:**

<img width="485" height="66" alt="image" src="https://github.com/user-attachments/assets/295c304d-6a51-4135-8a15-b328a99a8e29" />


## **Why Use NumPy?**

* **Performance:** NumPy arrays are stored in a contiguous block of memory and are implemented in C, making them significantly faster than Python lists for numerical operations.
* **Vectorization:** NumPy allows you to perform operations on entire arrays at once, without the need for explicit loops. This "vectorized" approach simplifies code and improves performance.
* **Broadcasting:** This feature allows NumPy to work with arrays of different shapes when performing arithmetic operations, making code more concise and readable.
* **Powerful Functions:** The library includes a vast collection of functions for linear algebra, Fourier transforms, random number generation, and more.

**NumPy is usually imported under the np alias**

Create an alias with the **as** keyword while importing:

```
import numpy as np
```
**Example:**

```
import numpy as np

arry = np.array([1,2,3,4]) ## one dimensional array

print(arry)
print(type(arry))
```

**Checking NumPy Version**

The version string is stored under __version__ attribute.
```
import numpy as np

print(np.__version__)
```
Output:

<img width="337" height="47" alt="image" src="https://github.com/user-attachments/assets/4f06bf6c-927e-4791-a3ab-3eee13d4ea98" />

## Creating Arrays Using NumPy:

* NumPy is used to work with arrays. The array object in NumPy is called **ndarray**. 
* We can create a NumPy ndarray object by using the array() function.

**Note:**

To create an ndarray, we can pass a list, tuple or any array-like object into the array() method, and it will be converted into an ndarray:

```
import numpy as np
print(np.__version__)

print("#####################")

arry = np.array((1,2,3,4,5)) ## passing tuple of elements to array function
print(arry)

print("#####################")

arry2 = np.array([1,2,3,4]) ## passing list of elements to array function
print(arry2)
```

**Output:**

<img width="525" height="115" alt="image" src="https://github.com/user-attachments/assets/e40bcf1e-eb8a-4e31-ba09-622a7cd591ab" />

### **Dimensions in Arrays**:

A dimension in arrays is one level of array depth (nested arrays)

### **0-D Arrays**:

0-D arrays, or Scalars, are the elements in an array. Each value in an array is a 0-D array.

Example:
```
import numpy as np
arry = np.array([56])  # O-D array
print(arry)
```

Output:

<img width="434" height="40" alt="image" src="https://github.com/user-attachments/assets/d194ac72-d9f0-46a1-affd-70e2f917cf9c" />

### 1-D Arrays:

* An array that has 0-D arrays as its elements is called uni-dimensional or 1-D array.
* These are the most common and basic arrays.

Create a 1-D array containing the values 10,20,30,40,50:
```
import numpy as np

arry = np.array([10,20,30,40,50])

print(arry)
```

Output:

<img width="462" height="49" alt="image" src="https://github.com/user-attachments/assets/10ea0c3c-1018-4278-86e8-47fd6ee4be6e" />

### 2-D Arrays:

* An array that has 1-D arrays as its elements is called a 2-D array.
* These are often used to represent matrix or 2nd order tensors.

Create a 2-D array containing two arrays with the values 10,20,30 and 40,50,60:
```
import numpy as np

arry = np.array([[10,20,30], [40,50,60]])

print(arry)
```

Output:

<img width="465" height="55" alt="image" src="https://github.com/user-attachments/assets/1c3e2164-60e0-4bc2-9461-a658761458d5" />

### 3-D arrays:
   
* An array that has 2-D arrays (matrices) as its elements is called 3-D array.
* These are often used to represent a 3rd order tensor.

Create a 3-D array with two 2-D arrays, both containing two arrays with the values 1,2,3 and 4,5,6:
```
import numpy as np

arry = np.array([[[10,20,30], [40,50,60]],[[10,20,30],[40,50,60]]])

print(arry)
```
Output:

<img width="519" height="127" alt="image" src="https://github.com/user-attachments/assets/6253271e-8092-4e09-a623-6f1c030f6308" />

**Check Number of Dimensions?**

Example:
```
import numpy as np

a = np.array([5])
b = np.array([1,2,3])
c = np.array([[1,2],[3,4]])
d = np.array([[[1,2],[3,4]],[[1,2],[3,4]]])

print(a.ndim)
print(b.ndim)
print(c.ndim)
print(d.ndim)
```

Output:

<img width="454" height="92" alt="image" src="https://github.com/user-attachments/assets/4d06aad6-44ad-4714-ab59-ddc5a4f45a16" />

### Higher Dimensional Arrays:

* An array can have any number of dimensions.
* When the array is created, you can define the number of dimensions by using the **ndmin** argument.

Create an array with 5 dimensions and verify that it has 5 dimensions:
```
import numpy as np

arry = np.array([1,2,3,4,5], ndmin=5)

print(arry)
print("number of dimensions of the array", arry.ndim)
```

Output:

<img width="543" height="73" alt="image" src="https://github.com/user-attachments/assets/6e532230-1a22-42d3-8a03-3dcfdc438f4f" />

In this array the innermost dimension (5th dim) has 4 elements, the 4th dim has 1 element that is the vector, the 3rd dim has 1 element that is the matrix with the vector, the 2nd dim has 1 element that is 3D array and 1st dim has 1 element that is a 4D array.

## NumPy Array Indexing:

### Access Array Elements:
* Array indexing is the same as accessing an array element.
* You can access an array element by referring to its index number.
* The indexes in NumPy arrays start with 0, meaning that the first element has index 0, and the second has index 1 etc.

Example:
```
import numpy as np

arry = np.array([1,2,3,4,5])

print(arry)

print(arry[0])
print(arry[4])
print(arry[0] + arry[4])
print(arry[3] - arry[0])
```

Output:

<img width="519" height="117" alt="image" src="https://github.com/user-attachments/assets/7774a897-c818-42ea-a8ed-335e4474b215" />

### Access 2-D Arrays:

* To access elements from 2-D arrays we can use comma separated integers representing the dimension and the index of the element.
* Think of 2-D arrays like a table with rows and columns, where the dimension represents the row and the index represents the column.

Example: arry[row, col]
```
import numpy as np

arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])

print('2nd element on 1st row: ', arr[0, 1])

arr2 = np.array([[1,2,3,4,5], [6,7,8,9,10]])

print('5th element on 2nd row: ', arr[1, 4])
```

Output:

<img width="508" height="65" alt="image" src="https://github.com/user-attachments/assets/fb1d69e7-2858-47c4-a574-f5028851fb6f" />

### Access 3-D Arrays:

To access elements from 3-D arrays we can use comma separated integers representing the dimensions and the index of the element.

Example;

Access the third element of the second array of the first array:
arry[row, col, index]
```
import numpy as np

arr = np.array([[[1, 2, 3], [4, 5, 6]], 
                [[7, 8, 9], [10, 11, 12]]])

print(arr[0, 1, 2])
```

Output:

<img width="424" height="48" alt="image" src="https://github.com/user-attachments/assets/c6ba0ef4-b65f-4046-9ba8-c47cea70c714" />

### Negative Indexing:

Use negative indexing to access an array from the end.

Example:

Print the last element from the 2nd dim:
```
import numpy as np

arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])

print('Last element from 2nd dim: ', arr[1, -1])
```

Output:

<img width="418" height="42" alt="image" src="https://github.com/user-attachments/assets/58ffb38a-ed40-445a-9e56-095095d4f0e4" />

## NumPy Array Slicing:

### Slicing arrays:

* Slicing in python means taking elements from one given index to another given index.
* We pass slice instead of index like this: [start:end].
* We can also define the step, like this: [start:end:step].
* If we don't pass start its considered 0
* If we don't pass end its considered length of array in that dimension
* If we don't pass step its considered 1

Example:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7])

print(arr[1:5])
print(arr[4:])
print(arr[:4])
```

Output:

<img width="450" height="88" alt="image" src="https://github.com/user-attachments/assets/3ad6b1bd-67ca-48f3-99bb-6c39d7c56d5b" />

#### Negative Slicing:

Use the minus operator to refer to an index from the end:

Example:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7])

print(arr[-3:-1])
```

Output:

<img width="421" height="46" alt="image" src="https://github.com/user-attachments/assets/1c4cf664-f147-44bf-8e8d-7527623fff0e" />

#### STEP:

Use the step value to determine the step of the slicing:

Example:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7])

print(arr[1:5:2])

print(arr[::2])
```

Output:

<img width="459" height="58" alt="image" src="https://github.com/user-attachments/assets/090a8417-9b57-45bc-97dc-1c74cef27002" />

#### Slicing 2-D Arrays:

Example:
```
import numpy as np

arr = np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])

print("From the second element, slice elements from index 1 to index 4 (not included):")
print(arr[1, 1:4])

print("From both elements, return index 2:")
print(arr[0:2, 2])

print("From both elements, slice index 1 to index 4 (not included), this will return a 2-D array:")
print(arr[0:2, 1:4])
```
#### Slicing 2-D Arrays:
Output:

<img width="856" height="166" alt="image" src="https://github.com/user-attachments/assets/db025e9e-95d3-4718-93f5-0eea12ed4399" />

## NumPy Data Types:

**Data Types in Python**:

By default Python have these data types:

* strings - used to represent text data, the text is given under quote marks. e.g. "ABCD"
* integer - used to represent integer numbers. e.g. -1, -2, -3
* float - used to represent real numbers. e.g. 1.2, 42.42
* boolean - used to represent True or False.
* complex - used to represent complex numbers. e.g. 1.0 + 2.0j, 1.5 + 2.5j

**Data Types in NumPy**:

NumPy has some extra data types, and refer to data types with one character, like i for integers, u for unsigned integers etc.

Below is a list of all data types in NumPy and the characters used to represent them.

* i - integer
* b - boolean
* u - unsigned integer
* f - float
* c - complex float
* m - timedelta
* M - datetime
* O - object
* S - string
* U - unicode string
* V - fixed chunk of memory for other type ( void )


### Checking the Data Type of an Array:

The NumPy array object has a property called dtype that returns the data type of the array:

```
import numpy as np

arr = np.array([1, 2, 3, 4])
print(arr.dtype)

arr1 = np.array(['apple', 'banana', 'cherry'])
print(arr1.dtype)
```

Output:

<img width="398" height="66" alt="image" src="https://github.com/user-attachments/assets/a951253f-f48a-4462-8479-7496b8b08426" />

### Creating Arrays With a Defined Data Type:

We use the array() function to create arrays, this function can take an optional argument: dtype that allows us to define the expected data type of the array elements:

```
import numpy as np

arr = np.array([1, 2, 3, 4], dtype='S')

print(arr)
print(arr.dtype)

arr1 = np.array([1, 2, 3, 4], dtype='i4')

print(arr1)
print(arr1.dtype)
```

Output:

<img width="506" height="102" alt="image" src="https://github.com/user-attachments/assets/c8dd21f2-7036-4f8c-ac9f-405385be7488" />

### Converting Data Type on Existing Arrays:

* The best way to change the data type of an existing array, is to make a copy of the array with the astype() method.
* The astype() function creates a copy of the array, and allows you to specify the data type as a parameter.
* The data type can be specified using a string, like 'f' for float, 'i' for integer etc. or you can use the data type directly like float for float and int for integer.

```
import numpy as np

arr = np.array([1.1, 2.1, 3.1])

newarr = arr.astype('i')

print(newarr)
print(newarr.dtype)

arr1 = np.array([1.1, 2.1, 3.1])

newarr1 = arr1.astype(int)

print(newarr1)
print(newarr1.dtype)

arr2 = np.array([1, 0, 3])

newarr2 = arr2.astype(bool)

print(newarr2)
print(newarr2.dtype)
```

Output:

<img width="554" height="145" alt="image" src="https://github.com/user-attachments/assets/daeeb574-4d59-4f46-92ed-26fa02ba029a" />


### **copy() vs view() in NumPy**

In NumPy, copy and view refer to how arrays are duplicated or referenced. Understanding the difference is essential to avoid unexpected behavior when modifying arrays.

| Feature                      | `copy()`                           | `view()` (or slicing)                               |
| ---------------------------- | ---------------------------------- | --------------------------------------------------- |
| **Data duplication**         | Creates a new, independent array   | Shares the same data as the original                |
| **Memory**                   | Takes additional memory            | No extra memory for data                            |
| **Changes affect original?** | ❌ No                               | ✅ Yes (changes in the view reflect in the original) |
| **Use case**                 | When you want an independent array | When you want a window into the same data           |
| **Function used**            | `np.copy()` or `.copy()`           | `.view()` or slicing (e.g., `a[1:3]`)               |

**COPY():**

**Example-1:**

```
import numpy as np

a = np.array([1,2,3,4,5])
b = a.copy()
print("Testing the changes to 'b (copy)' will effect 'a' or not")
print("                                      ")
b[0] = 0
print("a = ", a)
print("b = ", b)
```
**Output:**

<img width="442" height="82" alt="image" src="https://github.com/user-attachments/assets/64642204-615a-4c5d-a3e9-3e6f925d7bf7" />

b is a copy, so changing b doesn't affect a and vice versa

**Example-2:**

```
import numpy as np

a = np.array([1,2,3,4,5])
b = a.copy()
print("Testing the changes to 'a (original)' will effect 'b' or not")
print("                                      ")
a[0] = 0
print("a = ", a)
print("b = ", b)
```
**Output:**

<img width="467" height="76" alt="image" src="https://github.com/user-attachments/assets/023a3e6a-b43c-428b-9292-4ca9b7c8baa1" />

b is a copy, so changing **a** doesn't affect **b** and vice versa

**View():**

**Example-1:**

```
import numpy as np

a = np.array([1,2,3,4,5])
b = a.view()
print("Testing the changes to 'b (view)' will effect 'a' or not")
print("                                      ")
b[0] = 0
print("a = ", a)
print("b = ", b)
```
**Output:**

<img width="448" height="73" alt="image" src="https://github.com/user-attachments/assets/faa14027-d93a-45be-9787-baf0e099aeb3" />

b is a view, so changing b(view) will effect affect a and vice versa

**Example-2:**

```
import numpy as np

a = np.array([1,2,3,4,5])
b = a.view()
print("Testing the changes to 'a (original)' will effect 'b' or not")
print("                                      ")
a[0] = 0
print("a = ", a)
print("b = ", b)
```
**Output:**

<img width="481" height="72" alt="image" src="https://github.com/user-attachments/assets/5062b4a8-8f15-4b27-aa73-9239ddc33fef" />

b is a view, so changing **a** will affect **b** and vice versa

### **NumPy Array Shape:**

```
Shape of An Array - The shape of an array is the number of elements in each dimension.
```

**Get the Shape of an Array**

NumPy arrays have an attribute called shape that returns a tuple with each index having the number of corresponding elements.

**Example-1:**

```
import numpy as np

arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])

print(arr.shape)
```

**Output:**

<img width="691" height="48" alt="image" src="https://github.com/user-attachments/assets/10c41a3d-4f03-4287-8995-95185c99192e" />

**Example-2:**

```
import numpy as np

arr = np.array([1, 2, 3, 4], ndmin=5)

print(arr)
print('shape of array :', arr.shape)
```

**Output:**

<img width="681" height="68" alt="image" src="https://github.com/user-attachments/assets/4524c509-7b42-482d-8baf-cb7840866cb3" />

**Example-3:**

```
import numpy as np

##1D Array (Vector)
a = np.array([1, 2, 3, 4])
print(a.shape)  

#2D Array (Matrix)
b = np.array([[1, 2, 3],
              [4, 5, 6]])
print(b.shape)  

#3D Array (Tensor)
c = np.array([[[1, 2], [3, 4]],
              [[5, 6], [7, 8]]])
print(c.shape)
```

**Output:**

<img width="695" height="80" alt="image" src="https://github.com/user-attachments/assets/41e27e72-5920-489f-89a3-ca41a05c912e" />

**Note:**  2 blocks, each with 2 rows and 2 columns → shape is (2, 2, 2)

**Quick-Notes:** 

* array.ndim → Number of dimensions
* array.size → Total number of elements
* array.shape[i] → Size of dimension i

### NumPy Array Reshaping:

* Reshaping means changing the shape of an array.
* The shape of an array is the number of elements in each dimension.
* By reshaping we can add or remove dimensions or change number of elements in each dimension.

**Reshape From 1-D to 2-D:**

```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])

newarr = arr.reshape(4, 3)

print(newarr)
```

**Output:**

<img width="743" height="112" alt="image" src="https://github.com/user-attachments/assets/7cf89a62-f4fe-4d00-baa3-10866667f40d" />

**Reshape From 1-D to 3-D:**

```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12])

newarr = arr.reshape(2, 3, 2)

print(newarr)
```
**Output:**

<img width="614" height="169" alt="image" src="https://github.com/user-attachments/assets/2c5247de-d3b7-497a-94ce-615ffe905c55" />

**Unknown Dimension**

* You are allowed to have one "unknown" dimension.
* Meaning that you do not have to specify an exact number for one of the dimensions in the reshape method.
* Pass -1 as the value, and NumPy will calculate this number for you.

**Example:**

```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])

newarr = arr.reshape(2, 2, -1)

print(newarr)
```

**Output:**

<img width="805" height="130" alt="image" src="https://github.com/user-attachments/assets/6f36617c-d605-44aa-bedf-76b4bfecb39c" />

**Flattening the arrays**

* Flattening array means converting a multidimensional array into a 1D array.
* We can use reshape(-1) to do this.

**Example:**
```
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])

newarr = arr.reshape(-1)

print(newarr)
```

**Output:**

<img width="515" height="52" alt="image" src="https://github.com/user-attachments/assets/33179379-7f74-45c1-b797-ea7131f28662" />

**Summary:**

| Operation                    | Function                   |
| ---------------------------- | -------------------------- |
| Reshape array                | `reshape()`                |
| Flatten array                | `reshape(-1)` or `ravel()` |
| Let NumPy decide a dimension | Use `-1`                   |


### NumPy Array Iterating:

**Iterating Arrays**

* Iterating means going through elements one by one.
* As we deal with multi-dimensional arrays in numpy, we can do this using basic for loop of python.
* If we iterate on a 1-D array it will go through each element one by one.

**Example**:

Iterate on the elements of the following 1-D array:
```
import numpy as np

arr = np.array([1, 2, 3])

for x in arr:
  print(x)
```
**Output:**

<img width="581" height="85" alt="image" src="https://github.com/user-attachments/assets/960c8ec9-6638-4776-b6e3-6998fa858a38" />

**Iterating 2-D Arrays**:

In a 2-D array it will go through all the rows.
```
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])

for x in arr:
  print(x)
```

**Output:**

<img width="642" height="64" alt="image" src="https://github.com/user-attachments/assets/2cd22159-c1ea-45c3-8eeb-5e5d54a20700" />

**Note:** To return the actual values, the scalars, we have to iterate the arrays in each dimension.

Iterate on each scalar element of the 2-D array:
```
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])

for x in arr:
  for y in x:
    print(y)
```

**Output:**

<img width="677" height="138" alt="image" src="https://github.com/user-attachments/assets/69d9174f-d46f-4f80-be02-bf89bac2430f" />


**Iterating 3-D Arrays**

In a 3-D array it will go through all the 2-D arrays.
```
import numpy as np

arr = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

for x in arr:
  print(x)
```

**Output:**

<img width="673" height="100" alt="image" src="https://github.com/user-attachments/assets/d320c786-d325-4ca2-908b-20b768534832" />

To return the actual values, the scalars, we have to iterate the arrays in each dimension.
```
import numpy as np

arr = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

for x in arr:
  for y in x:
    for z in y:
      print(z)
```

**Output:**

<img width="721" height="252" alt="image" src="https://github.com/user-attachments/assets/bbd90c88-6ab0-4ec7-9f39-ccb636c7e9e5" />


**Iterating Arrays Using nditer()**

The function nditer() is a helping function that can be used from very basic to very advanced iterations. It solves some basic issues which we face in iteration, lets go through it with examples.

**Iterating on Each Scalar Element**

In basic for loops, iterating through each scalar of an array we need to use n for loops which can be difficult to write for arrays with very high dimensionality.

Iterate through the following 3-D array:
```
import numpy as np

arr = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])

for x in np.nditer(arr):
  print(x)
```

**Output:**

<img width="691" height="169" alt="image" src="https://github.com/user-attachments/assets/0ce2d7bf-2819-428c-941b-4caaece6cece" />

**Iterating Array With Different Data Types**

We can use op_dtypes argument and pass it the expected datatype to change the datatype of elements while iterating.

NumPy does not change the data type of the element in-place (where the element is in array) so it needs some other space to perform this action, that extra space is called buffer, and in order to enable it in nditer() we pass flags=['buffered'].

Iterate through the array as a string:
```
import numpy as np

arr = np.array([1, 2, 3])

for x in np.nditer(arr, flags=['buffered'], op_dtypes=['S']):
  print(x)
```

**Output:**

<img width="592" height="90" alt="image" src="https://github.com/user-attachments/assets/7162960a-3ec9-40a4-9b3f-64289f247ab8" />

**Iterating With Different Step Size:**

We can use filtering and followed by iteration.

Iterate through every scalar element of the 2D array skipping 1 element:
```
import numpy as np

arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])

for x in np.nditer(arr[:, ::2]):
  print(x)
```
**Output:**

<img width="589" height="102" alt="image" src="https://github.com/user-attachments/assets/86ff93df-6eec-46cc-a3aa-231b68700725" />


**Enumerated Iteration Using ndenumerate():**

* Enumeration means mentioning sequence number of somethings one by one.
* Sometimes we require corresponding index of the element while iterating, the ndenumerate() method can be used for those usecases.

Enumerate on following 1D arrays elements:
```
import numpy as np

arr = np.array([1, 2, 3])

for idx, x in np.ndenumerate(arr):
  print(idx, x)
```

**Output:**

<img width="531" height="88" alt="image" src="https://github.com/user-attachments/assets/9b1e634a-dffa-44a3-97dc-abac7e0b2015" />


Enumerate on following 2D array's elements:
```
import numpy as np

arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])

for idx, x in np.ndenumerate(arr):
  print(idx, x)
```

**Output:**

<img width="699" height="173" alt="image" src="https://github.com/user-attachments/assets/b1ebe7c8-7e7c-4fbc-825c-d44dd7f56bc5" />


### NumPy Joining Array:

**Joining NumPy Arrays**

* Joining means putting contents of two or more arrays in a single array.
* In SQL we join tables based on a key, whereas in NumPy we join arrays by axes.
* We pass a sequence of arrays that we want to join to the concatenate() function, along with the axis. If axis is not explicitly passed, it is taken as 0.

Joining two arrays:
```
import numpy as np

arr1 = np.array([1, 2, 3])

arr2 = np.array([4, 5, 6])

arr = np.concatenate((arr1, arr2))

print(arr)
```

**Output:**

<img width="607" height="54" alt="image" src="https://github.com/user-attachments/assets/4ad06eb1-2700-42b7-9d37-c6d78bd75876" />

Join two 2-D arrays along rows (axis=1):
```
import numpy as np

arr1 = np.array([[1, 2], [3, 4]])

arr2 = np.array([[5, 6], [7, 8]])

arr = np.concatenate((arr1, arr2), axis=1)

print(arr)
```

**Output:**

<img width="568" height="67" alt="image" src="https://github.com/user-attachments/assets/1194fb54-16c2-4953-bc8d-a6983b0dd8c9" />

**Joining Arrays Using Stack Functions:**

* Stacking is same as concatenation, the only difference is that stacking is done along a new axis.
* We can concatenate two 1-D arrays along the second axis which would result in putting them one over the other, ie. stacking.
* We pass a sequence of arrays that we want to join to the stack() method along with the axis. If axis is not explicitly passed it is taken as 0.

```
import numpy as np

arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

arr = np.stack((arr1, arr2), axis=0)
print(arr)
print("               ")

arr = np.stack((arr1, arr2), axis=1)
print(arr)
```

**Output:**

<img width="583" height="134" alt="image" src="https://github.com/user-attachments/assets/34e35d60-78aa-4758-8f29-bccb3e12850f" />


**Stacking Along Rows**:

NumPy provides a helper function: hstack() to stack along rows.
```
import numpy as np

arr1 = np.array([1, 2, 3])

arr2 = np.array([4, 5, 6])

arr = np.hstack((arr1, arr2))

print(arr)
```

**Output:**

<img width="551" height="46" alt="image" src="https://github.com/user-attachments/assets/103e0667-8ac7-4e24-aa2c-01bba8241662" />

**Stacking Along Columns**:

NumPy provides a helper function: vstack()  to stack along columns.
```
import numpy as np

arr1 = np.array([1, 2, 3])

arr2 = np.array([4, 5, 6])

arr = np.vstack((arr1, arr2))

print(arr)
```

**Output:**

<img width="559" height="69" alt="image" src="https://github.com/user-attachments/assets/cc462b40-418d-45dd-be8f-0ce1ae67f4ba" />


**Stacking Along Height (depth)**

NumPy provides a helper function: dstack() to stack along height, which is the same as depth.
```
import numpy as np

arr1 = np.array([1, 2, 3])

arr2 = np.array([4, 5, 6])

arr = np.dstack((arr1, arr2))

print(arr)
```

**Output:**

<img width="542" height="90" alt="image" src="https://github.com/user-attachments/assets/4c4fd48a-db88-4c64-8222-29e32717c7b1" />

### NumPy Splitting Array:

**Splitting NumPy Arrays**

* Splitting is reverse operation of Joining.
* Joining merges multiple arrays into one and Splitting breaks one array into multiple.
* We use array_split() for splitting arrays, we pass it the array we want to split and the number of splits.

**Example:**

```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6])

newarr = np.array_split(arr, 3)
print(newarr)

print(" ")
##If the array has less elements than required, it will adjust from the end accordingly.
newarr = np.array_split(arr, 4)
print(newarr)
```

**Output:**

<img width="680" height="96" alt="image" src="https://github.com/user-attachments/assets/b0d7d5a9-6e8e-48c8-8693-fac5561200a4" />

### NumPy Searching Arrays:

**Searching Arrays**

* You can search an array for a certain value, and return the indexes that get a match.
* To search an array, use the where() method.

**Example:1**

Find the indexes where the value is 4:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 4, 4])

x = np.where(arr == 4)

print(x)
```

**Output:**

<img width="559" height="50" alt="image" src="https://github.com/user-attachments/assets/4f47518c-c252-4f9e-9b0d-c2e6734a8ddb" />


The example above will return a tuple: (array([3, 5, 6],)

Which means that the value 4 is present at index 3, 5, and 6.


**Example:2**

Find the indexes where the values are even:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])

x = np.where(arr%2 == 0)

print(x)
```

**Output:**

<img width="500" height="49" alt="image" src="https://github.com/user-attachments/assets/e35e73b3-fff9-48fa-a0e9-9ac11c8dc794" />


**Example:3**

Find the indexes where the values are odd:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])

x = np.where(arr%2 == 1)

print(x)
```

**Output:**

<img width="538" height="56" alt="image" src="https://github.com/user-attachments/assets/df69dee6-62c7-4411-b042-c78d8568029f" />

### NumPy Sorting Arrays:

* Sorting means putting elements in an ordered sequence.
* Ordered sequence is any sequence that has an order corresponding to elements, like numeric or alphabetical, ascending or descending.
* The NumPy ndarray object has a function called sort(), that will sort a specified array.

```
import numpy as np

arr = np.array([3, 2, 0, 1])
print(np.sort(arr))

arr = np.array(['banana', 'cherry', 'apple'])
print(np.sort(arr))

arr = np.array([True, False, True])
print(np.sort(arr))

arr = np.array([[3, 2, 4], [5, 0, 1]])
print(np.sort(arr))
```

**Output:**

<img width="665" height="121" alt="image" src="https://github.com/user-attachments/assets/917da256-20d1-41ca-91f5-8f805ac038ff" />

### NumPy Filter Array:

**Filtering Arrays**

* Getting some elements out of an existing array and creating a new array out of them is called filtering.
* In NumPy, you filter an array using a boolean index list.

If the value at an index is True that element is contained in the filtered array, if the value at that index is False that element is excluded from the filtered array.
```
import numpy as np

arr = np.array([41, 42, 43, 44])

x = [True, False, True, False]

newarr = arr[x]

print(newarr)
```

**Output:**

<img width="513" height="57" alt="image" src="https://github.com/user-attachments/assets/ff133061-8694-401b-8246-b104782be91a" />

**Creating the Filter Array**

In the example above we hard-coded the True and False values, but the common use is to create a filter array based on conditions.

```
import numpy as np

arr = np.array([41, 42, 43, 44])

# Create an empty list
filter_arr = []

# go through each element in arr
for element in arr:
  # if the element is higher than 42, set the value to True, otherwise False:
  if element > 42:
    filter_arr.append(True)
  else:
    filter_arr.append(False)

newarr = arr[filter_arr]

print(filter_arr)
print(newarr)
```

**Output:**

<img width="591" height="66" alt="image" src="https://github.com/user-attachments/assets/58421a45-55a8-4b16-8898-e6db34907034" />

Create a filter array that will return only even elements from the original array:
```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7])

# Create an empty list
filter_arr = []

# go through each element in arr
for element in arr:
  # if the element is completely divisble by 2, set the value to True, otherwise False
  if element % 2 == 0:
    filter_arr.append(True)
  else:
    filter_arr.append(False)

newarr = arr[filter_arr]

print(filter_arr)
print(newarr)
```

**Output:**

<img width="511" height="60" alt="image" src="https://github.com/user-attachments/assets/e6f881bf-9ecd-40d0-9620-0a37cf88a113" />

**Creating Filter Directly From Array**

* The above example is quite a common task in NumPy and NumPy provides a nice way to tackle it.
* We can directly substitute the array instead of the iterable variable in our condition and it will work just as we expect it to.

```
import numpy as np

arr = np.array([41, 42, 43, 44])

filter_arr = arr > 42

newarr = arr[filter_arr]

print(filter_arr)
print(newarr)
```

**Output:**

<img width="569" height="65" alt="image" src="https://github.com/user-attachments/assets/382f3976-0f03-4843-b23f-2d21a357590e" />


```
import numpy as np

arr = np.array([1, 2, 3, 4, 5, 6, 7])

# Create an empty list
filter_arr = arr%2 ==0

newarr = arr[filter_arr]

print(filter_arr)
print(newarr)
```

**Output:**

<img width="511" height="60" alt="image" src="https://github.com/user-attachments/assets/e6f881bf-9ecd-40d0-9620-0a37cf88a113" />


## NumPy Random:

**What is a Random Number?**

Random number does NOT mean a different number every time. Random means something that can not be predicted logically.

**Pseudo Random and True Random.**

* Computers work on programs, and programs are definitive set of instructions. So it means there must be some algorithm to generate a random number as well.
* If there is a program to generate random number it can be predicted, thus it is not truly random.

Random numbers generated through a generation algorithm are called pseudo random.

**Can we make truly random numbers?**

Yes. In order to generate a truly random number on our computers we need to get the random data from some outside source. This outside source is generally our keystrokes, mouse movements, data on network etc.

We do not need truly random numbers, unless it is related to security (e.g. encryption keys) or the basis of application is the randomness (e.g. Digital roulette wheels).

In this tutorial we will be using pseudo random numbers.

```
from numpy import random

#Generate a random integer from 0 to 100:
x = random.randint(100)
print(x)
print(" ")
#Generate a random float from 0 to 1:
x = random.rand(2)
print(x)
print(" ")
x = random.rand(5)
print(x)
print(" ")
#Generate a 1-D array containing 5 random integers from 0 to 100:
x=random.randint(100, size=(5))
print(x)
print(" ")
#Generate a 2-D array with 3 rows, each row containing 5 random integers from 0 to 100:
x = random.randint(100, size=(3, 5))
print(x)
print(" ")
#Generate a 2-D array with 3 rows, each row containing 5 random float numbers:
x = random.rand(3, 5)
print(x)
print(" ")
#The choice() method allows you to generate a random value based on an array of values.
#The choice() method takes an array as a parameter and randomly returns one of the values.
x = random.choice([3, 5, 7, 9])
print(x)
print(" ")
#Generate a 2-D array that consists of the values in the array parameter (3, 5, 7, and 9):
x = random.choice([3, 5, 7, 9], size=(3, 5))
print(x)
```

**Output:**

<img width="844" height="430" alt="image" src="https://github.com/user-attachments/assets/26ba3471-c05f-4da0-8a0a-d66142723797" />


