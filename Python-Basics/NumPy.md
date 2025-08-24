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


