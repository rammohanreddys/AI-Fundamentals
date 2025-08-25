# NumPy Basics

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

### NumPy Array Indexing:

#### Access Array Elements:
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

#### Access 2-D Arrays:

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

#### Access 3-D Arrays:

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

### NumPy Array Slicing:

#### Slicing arrays:

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



























































