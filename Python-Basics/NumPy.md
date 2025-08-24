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





























































