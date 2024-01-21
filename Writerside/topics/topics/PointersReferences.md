# Pointers and References

<video src="https://youtu.be/sxHng1iufQE?feature=shared" preview-src="pointersReferences.jpeg" width="900"/>

## Pointers

A pointer is a variable that stores the address of another variable. Unlike references, pointers can be assigned NULL value, can be assigned a different variable later in the program, and can be used to access the memory it points to.

``` c++
int x = 10;
int* ptr = &x; // ptr is a pointer to x.
```

The address of a variable can be obtained by preceding the name of a variable with an ampersand sign ( &amp; ), known as address-of operator.

``` c++
int x = 10;
int* ptr = &x; // ptr is a pointer to x.
```

The value of a variable can be obtained by preceding the name of a pointer with an asterisk sign (*), known as dereferencing operator.

``` c++
int x = 10;
int* ptr = &x; // ptr is a pointer to x.
cout << *ptr; // Prints 10
```

The value of a variable can be changed by assigning a new value using the dereferencing operator.

``` c++
int x = 10;
int* ptr = &x; // ptr is a pointer to x.
*ptr = 20; // Value of x is now changed to 20
```

A pointer can be assigned NULL value.

``` c++
int x = 10;
int* ptr = NULL; // ptr is a pointer that is pointing to NULL.
```

A pointer can be reassigned to point to another variable.

``` c++
int x = 10;
int y = 20;
int* ptr = &x; // ptr is a pointer to x.
ptr = &y; // ptr is now pointing to y.
```

A pointer need not be initialized when declared. There is no such restriction with references.

``` c++
int x = 10;
int& ref = x; // Correct. A reference must be initialized when declared.
int* ptr; // Correct. A pointer need not be initialized when declared.
```

A pointer can be used in a switch statement.

``` c++
int x = 10;
int* ptr = &x; // ptr is a pointer to x.
switch (*ptr) {
    case 10:
        cout << "Value of x is 10";
        break;
    default:
        cout << "Value of x is not 10";
}
```

A pointer can be used to allocate memory dynamically.

``` c++
int* ptr = new int; // ptr is a pointer to an integer allocated on the heap.
```

A pointer can be used to access the memory it points to.

``` c++
int* ptr = new int; // ptr is a pointer to an integer allocated on the heap.
*ptr = 10; // Value of the integer allocated on the heap is now 10
```


## References

A reference variable is an alias, that is, another name for an already existing variable. A reference, like a pointer, is also implemented by storing the address of an object.
A reference can be thought of as a constant pointer (not to be confused with a pointer to a constant value!) with automatic indirection, i.e., the compiler will apply the * operator for you. 

``` c++
int x = 10;
int& ref = x; // ref is a reference to x.
```

The reference is bound to the object at the time of initialization. All operations on the reference are actually performed on the object itself.

``` c++
int x = 10;
int& ref = x; // ref is a reference to x.
ref = 20; // Value of x is now changed to 20
x = 30; // Value of ref is now changed to 30
```

A reference once initialized to an object cannot be changed to refer to another object. Pointers can be pointed to another object at any time.

``` c++
int x = 10;
int y = 20;
int& ref = x; // ref is a reference to x.
ref = y; // x value is now changed to 20
```

A reference must be initialized when declared. There is no such restriction with pointers.

``` c++
int x = 10;
int& ref; // Error. A reference must be initialized when declared.
int* ptr; // Correct. A pointer need not be initialized when declared.
```

A reference cannot be NULL. Pointers are often made NULL to indicate that they are not pointing to any valid thing.

``` c++
int x = 10;
int& ref = x; // ref is a reference to x.
int* ptr = NULL; // ptr is a pointer that is pointing to NULL.
```

## References vs Pointers

<table>
    <tr>
        <th>Category</th>
        <th>References</th>
        <th>Pointers</th>
    </tr>
    <tr>
        <td>What is it?</td>
        <td>A reference is an alias, or an alternate name to an existing variable.</td>
        <td>A pointer is a variable that holds a memory address.</td>
    </tr>
    <tr>
        <td>How is it declared?</td>
        <td>int&amp; ref = x;</td>
        <td>int* ptr = &amp;x;</td>
    </tr>
    <tr>
        <td>What is the syntax for accessing the value pointed to by it?</td>
        <td>ref</td>
        <td>*ptr</td>
    </tr>
    <tr>
        <td>What is the syntax for accessing the address of it?</td>
        <td>&ref</td>
        <td>ptr</td>
    </tr>
    <tr>
        <td>What is the syntax for changing the value pointed to by it?</td>
        <td>ref = y;</td>
        <td>*ptr = y;</td>
    </tr>
    <tr>
        <td>What is the syntax for changing the address it is pointing to?</td>
        <td>Not possible</td>
        <td>ptr = &amp;y;</td>
    </tr>
    <tr>
        <td>Can it be NULL?</td>
        <td>No</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Can it be reassigned?</td>
        <td>No</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Can it be used in a switch statement?</td>
        <td>No</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Can it be used to allocate memory?</td>
        <td>No</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Can it be used to access the memory it points to?</td>
        <td>Yes</td>
        <td>Yes</td>
    </tr>
</table>




