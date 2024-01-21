# Lab 02 : Storing Data

## Introduction

Storing data in computer programming refers to the process of preserving and organizing information within a computer's memory or storage devices for future access and manipulation. It is a fundamental aspect of programming as it enables the software to work with and manage information efficiently. Data can represent various types of information, such as numbers, text, images, and more. In essence, data storage encompasses the methods and structures used to hold, retrieve, and manage data throughout the program's execution.



## Working with arrays

> In C++, an array is declared by specifying the data type of its elements, followed by the array's name and, optionally, its size. Here is the basic syntax for declaring an array in C++


### Pseudocode: array

```c++
data_type array_name[array_size];
```

<deflist>
<def title="data_type">
This represents the data type of the elements that the array will hold. It can be a fundamental data type like int, double, or char, or a user-defined data type, such as a structure or a class.
</def>
<def title="array_name">
This is the identifier or name given to the array, which allows you to refer to it in your code.
</def>
<def title="array_size">
This is the number of elements that the array can hold. It must be a non-negative integer, and it defines the size of the array. The array size can be a constant, a variable, or it can be omitted entirely when using fixed-size initialization.
</def>
</deflist>


### Fixed-Size Array Declaration

```c++
// specify the array size explicitly
int numbers[5];  // Declares an integer array named 'numbers' with a size of 5.
```


### Implicitly Sized Array Declaration

```c++
// provide an initialization list, the array size is automatically determined by the number of elements
int values[] = {10, 20, 30, 40, 50};  // The size is inferred as 5 based on the number of elements.
```


### Using a Variable for Array Size

```c++
// use a variable to specify the array size at runtime
int size = 10;
double data[size];  // Declares a double array named 'data' with a size determined by the 'size' variable.
```

<note>Remember that C++ arrays are zero-based, which means that the first element is at index 0, the second at index 1, 
and so on. Accessing elements outside the array bounds can lead to undefined behavior, so it's essential to ensure 
that your code remains within the defined array size.</note>
 
## Working with vectors

> A vector in C++ is a dynamic array-like container that can grow or shrink in size as needed. It's implemented as a template class, allowing you to store elements of various data types.


### Default Declaration

```c++
// declare an empty vector of a specific data type without specifying an initial size. The vector will automatically manage its size as elements are added.
#include <vector>
std::vector<int> myVector;  // Declares an empty integer vector.
```


### Declaration with Initial Size

```c++
// set the initial size of the vector, you can declare it with a specific number of elements
#include <vector>
std::vector<double> myVector(10);  // Declares a double vector with 10 default-initialized elements.
```


### Declaration with Initial Values

```c++
// initialize a vector with specific values using an initialization list. The vector size is determined by the number of elements in the list.
#include <vector>
std::vector<std::string> names = {"Alice", "Bob", "Charlie"};  // Declares a string vector with 3 elements.
```

### Using a List of Initializer Lists

```c++
// declare a vector of vectors (2D vector) or a vector of other collections using nested initializer lists.
#include <vector>
std::vector<std::vector<int>> matrix = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};  // 2D vector.
```


## Programming Requirements

### Problem 1



### Problem 2



### Problem 3



### Problem 4



### Problem 5



## Submission

- Open Gradescope
- Go to the respective lab 
- Submit each programed problem solution in to the respective input
- Click the submit button at the bottom of the page to save your entries



