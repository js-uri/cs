---
switcher-label: Language
---

# Collections



![image](collections.jpeg)

[//]: # (Alt image for java)
[//]: # (![java collections]&#40;https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210315172345/Java-Collections-Framework-Hierarchy.png&#41;)

[//]: # (Alt image for python)

## What is a collection in programming?

A collection is a group of items that are stored in a single object. The items in a collection are called elements or members of the collection. Collections are used to store, retrieve, manipulate, and communicate aggregate data. Typically, they represent data items that form a natural group, such as a poker hand (a collection of cards), a mail folder (a collection of letters), or a telephone directory (a mapping of names to phone numbers). 

## Linear v. Non-linear

These overarching collection categories are primarily defined how they are stored in contiguous memory.

<table>
<tr>
<td>Linear</td><td>Non-linear</td>
</tr>
<tr>
<td>

- are collections in which the elements are ordered sequentially. The order of the elements is determined by the order in which they are added to the collection. The elements in a linear collection can be accessed one at a time, in a specific order. 
- Examples of linear collections include `lists`*, `stacks`, `queues`, and `deques`.

*_\* Note: `list` naming convention and functionality will vary pending associated language_*  
</td>
<td>

- are collections in which the elements are not ordered sequentially. The order of the elements is determined by the relationship between the elements. The elements in a nonlinear collection can be accessed one at a time, in a specific order. Examples of nonlinear collections include trees and graphs.
</td>
</tr>
</table>


### Additional variances of collections

There are two main types of linear collections:

<table>
<tr>
<td>Sequential</td><td>Nonsequential</td>
</tr>
<tr>
<td>

- are collections in which the elements are ordered sequentially. The order of the elements is determined by the order in which they are added to the collection. The elements in a sequential collection can be accessed one at a time, in a specific order. Examples of sequential collections include lists, stacks, queues, and deques.
</td>
<td>

- are collections in which the elements are not ordered sequentially. The order of the elements is determined by the relationship between the elements. The elements in a nonsequential collection can be accessed one at a time, in a specific order. Examples of nonsequential collections include trees and graphs.
</td>
</tr>
</table>

### What are the different types of sequential collections?

There are two main types of sequential collections:

<table>
<tr>
<td>Indexed</td><td>Keyed</td>
</tr>
<tr>
<td>

- are collections in which the elements are accessed by an index. The order of the elements is determined by the index. The elements in an indexed collection can be accessed one at a time, in a specific order. Examples of indexed collections include arrays, lists, stacks, queues, deques, matrices, and tables.
</td>
<td>

- are collections in which the elements are accessed by a key. The order of the elements is determined by the key. The elements in a keyed collection can be accessed one at a time, in a specific order. Examples of keyed collections include dictionaries and hash tables.
</td>
</tr>
</table>

## Declaration v. Initialization

### Declaration

A declaration is a statement that associates an identifier with a type. A declaration introduces a name into a scope and may cause the construction of an object of the type to which the identifier refers.

### Initialization

Initialization is the process of locating and using the defined values for variable data that is used by a computer program. For example, an operating system or application program is installed with default or user-specified values that determine certain aspects of how the system or program is to function.

## Array : Declaration, Initialization, and further functionality

### What is an array?

An array is a collection of elements of the same type placed in contiguous memory locations that can be individually referenced by using an index to a unique identifier.

### Array Pseudocode {switcher-key="Pseudocode"}

```text

// Declaration
arrayName : arrayType [arraySize]

// Initialization
arrayName : arrayType [arraySize] = {value1, value2, value3, ...}

// Accessing an element
arrayName[index]

// Assigning a value to an element
arrayName[index] = value

```


### Array C++ {switcher-key="C++"}

<compare first-title="Pseudocode" second-title="C++">

```c++
// Declaration
arrayType arrayName [arraySize];

// Initialization
arrayType arrayName [arraySize] = {value1, value2, value3, ...};

// Accessing an element
arrayName[index];

// Assigning a value to an element
arrayName[index] = value;
```

```c++
#include <iostream>
using namespace std;

int main() {
    int array[5] = {1, 2, 3, 4, 5};
    cout << array[0] << endl;
    array[0] = 10;
    cout << array[0] << endl;
    return 0;
}
```

</compare>

#### Array Output C++ {switcher-key="C++"}

```c++
1
10
```

### Array Python {switcher-key="Python"}

<compare first-title="Pseudocode" second-title="Python">

```Python


```Python
# Declaration
arrayName = [value1, value2, value3, ...]

# Initialization
arrayName = [value1, value2, value3, ...]

# Accessing an element
arrayName[index]

# Assigning a value to an element
arrayName[index] = value
```

```Python
array = [1, 2, 3, 4, 5]
print(array[0])
array[0] = 10
print(array[0])
```

</compare>

#### Array Output Python {switcher-key="Python"}

```Python
1
10
```

### Array Java {switcher-key="Java"}

<compare first-title="Pseudocode" second-title="Java">

```java
// Declaration
arrayType[] arrayName = new arrayType[arraySize];

// Initialization
arrayType[] arrayName = {value1, value2, value3, ...};

// Accessing an element
arrayName[index];

// Assigning a value to an element
arrayName[index] = value;
```

```java
public class Main {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        System.out.println(array[0]);
        array[0] = 10;
        System.out.println(array[0]);
    }
}
```

</compare>

#### Array Output Java {switcher-key="Java"}

```java
1
10
```

### Array 1 Go {switcher-key="Go"}

<compare first-title="Pseudocode" second-title="Go">

```go
// Declaration
var arrayName [arraySize]arrayType

// Initialization
arrayName := [arraySize]arrayType{value1, value2, value3, ...}

// Accessing an element
arrayName[index]

// Assigning a value to an element
arrayName[index] = value
```

```go
package main

import "fmt"

func main() {
    array := [5]int{1, 2, 3, 4, 5}
    fmt.Println(array[0])
    array[0] = 10
    fmt.Println(array[0])
}
```

</compare>

#### Array Output Go {switcher-key="Go"}

```go
1
10
```

## List : Declaration, Initialization, and further functionality

### What is a list? how do they vary from arrays?

A list is a collection of elements of the same type placed in contiguous memory locations that can be individually referenced by using an index to a unique identifier. Lists are similar to arrays, but they are not the same. Lists are dynamic, meaning that they can grow and shrink in size. Arrays are static, meaning that they cannot grow or shrink in size. Lists are also more flexible than arrays. Lists can be used to implement stacks, queues, and deques. Arrays cannot be used to implement stacks, queues, and deques. 

### List Pseudocode {switcher-key="Pseudocode"}

```text

// Declaration
listName : listType

// Initialization
listName : listType = {value1, value2, value3, ...}

// Accessing an element
listName[index]

// Assigning a value to an element
listName[index] = value

// Adding an element
listName.add(value)

// Removing an element
listName.remove(index)

// Getting the size of the list
listName.size()

// Checking if the list is empty
listName.isEmpty()

// Checking if the list contains a value
listName.contains(value)

// Clearing the list
listName.clear()

```

### List C++ {switcher-key="C++"}

<compare first-title="Pseudocode" second-title="C++">

```c++
// Declaration
listType listName;

// Initialization
listType listName = {value1, value2, value3, ...};

// Accessing an element
listName[index];

// Assigning a value to an element
listName[index] = value;

// Adding an element
listName.push_back(value);

// Removing an element
listName.erase(listName.begin() + index);

// Getting the size of the list
listName.size();

// Checking if the list is empty
listName.empty();

// Checking if the list contains a value
std::find(listName.begin(), listName.end(), value) != listName.end();

// Clearing the list
listName.clear();
```

```c++
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> list = {1, 2, 3, 4, 5};
    std::cout << list[0] << std::endl;
    list[0] = 10;
    std::cout << list[0] << std::endl;
    list.push_back(6);
    std::cout << list[5] << std::endl;
    list.erase(list.begin() + 5);
    std::cout << list.size() << std::endl;
    std::cout << std::boolalpha << list.empty() << std::endl;
    std::cout << std::boolalpha << std::find(list.begin(), list.end(), 3) != list.end() << std::endl;
    list.clear();
    std::cout << list.size() << std::endl;
    return 0;
}
```

</compare>

#### List Output C++ {switcher-key="C++"}

```c++
1
10
6
5
false
true
0
```

### List Python {switcher-key="Python"}

<compare first-title="Pseudocode" second-title="Python">

```Python
# Declaration
listName = [value1, value2, value3, ...]

# Initialization
listName = [value1, value2, value3, ...]

# Accessing an element
listName[index]

# Assigning a value to an element
listName[index] = value

# Adding an element
listName.append(value)

# Removing an element
listName.pop(index)

# Getting the size of the list
len(listName)

# Checking if the list is empty
len(listName) == 0

# Checking if the list contains a value
value in listName

# Clearing the list
listName.clear()
```

```Python
list = [1, 2, 3, 4, 5]
print(list[0])
list[0] = 10
print(list[0])
list.append(6)
print(list[5])
list.pop(5)
print(len(list))
print(len(list) == 0)
print(3 in list)    
list.clear()
print(len(list))
```

</compare>

#### List Output Python {switcher-key="Python"}

```Python
1
10
6
5
False
True
0
```

### List Java {switcher-key="Java"}

<compare first-title="Pseudocode" second-title="Java">

```java
// Declaration
listType listName = new listType();

// Initialization
listType listName = {value1, value2, value3, ...};

// Accessing an element
listName.get(index);

// Assigning a value to an element
listName.set(index, value);

// Adding an element
listName.add(value);

// Removing an element
listName.remove(index);

// Getting the size of the list
listName.size();

// Checking if the list is empty
listName.isEmpty();

// Checking if the list contains a value
listName.contains(value);

// Clearing the list
listName.clear();
```

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        System.out.println(list.get(0));
        list.set(0, 10);
        System.out.println(list.get(0));
        list.add(6);
        System.out.println(list.get(5));
        list.remove(5);
        System.out.println(list.size());
        System.out.println(list.isEmpty());
        System.out.println(list.contains(3));
        list.clear();
        System.out.println(list.size());
    }
}
```

</compare>

#### List Output Java {switcher-key="Java"}

```java
1
10
6
5
false
true
0
```

### List Go {switcher-key="Go"}

<compare first-title="Pseudocode" second-title="Go">

```go
// Declaration
var listName []listType

// Initialization
listName := []listType{value1, value2, value3, ...}

// Accessing an element
listName[index]

// Assigning a value to an element
listName[index] = value

// Adding an element
listName = append(listName, value)

// Removing an element
listName = append(listName[:index], listName[index+1:]...)

// Getting the size of the list
len(listName)

// Checking if the list is empty
len(listName) == 0

// Checking if the list contains a value
value in listName

// Clearing the list
listName = nil
```

```go
package main

import "fmt"

func main() {
    list := []int{1, 2, 3, 4, 5}
    fmt.Println(list[0])
    list[0] = 10
    fmt.Println(list[0])
    list = append(list, 6)
    fmt.Println(list[5])
    list = append(list[:5], list[6:]...)
    fmt.Println(len(list))
    fmt.Println(len(list) == 0)
    fmt.Println(3 in list)
    list = nil
    fmt.Println(len(list))
}
```

</compare>

#### List Output Go {switcher-key="Go"}

```go
1
10
6
5
false
true
0
```

## Queue : Declaration, Initialization, and further functionality

### What is a queue?

A queue is a linear collection of elements that can be accessed only at one of its ends for storing and retrieving data. The end of the queue where elements are added is known as the back of the queue, and the end of the queue where elements are removed is known as the front of the queue. The order in which elements are added to the back of the queue is the same order in which they are removed from the front of the queue. This ordering is known as first-in, first-out (FIFO).

### Queue 1 Pseudocode {switcher-key="Pseudocode"}

```text

// Declaration
queueName : queueType

// Initialization
queueName : queueType = {value1, value2, value3, ...}

// Accessing an element
queueName[index]

// Assigning a value to an element
queueName[index] = value

// Adding an element
queueName.enqueue(value)

// Removing an element
queueName.dequeue()

// Getting the size of the queue
queueName.size()

// Checking if the queue is empty
queueName.isEmpty()

// Checking if the queue contains a value
queueName.contains(value)
 
// Clearing the queue
queueName.clear()

```

### Queue C++ {switcher-key="C++"}

<compare first-title="Pseudocode" second-title="C++">

```c++
// Declaration
queueType queueName;

// Initialization
queueType queueName = {value1, value2, value3, ...};

// Accessing an element
queueName[index];

// Assigning a value to an element
queueName[index] = value;

// Adding an element
queueName.push(value);

// Removing an element
queueName.pop();

// Getting the size of the queue
queueName.size();

// Checking if the queue is empty
queueName.empty();

// Checking if the queue contains a value
std::find(queueName.begin(), queueName.end(), value) != queueName.end();
    
// Clearing the queue
queueName.clear();
```

```c++
#include <iostream>
#include <queue>
#include <algorithm>

int main() {
    std::queue<int> queue;
    queue.push(1);
    queue.push(2);
    queue.push(3);
    queue.push(4);
    queue.push(5);
    std::cout << queue.front() << std::endl;
    queue.front() = 10;
    std::cout << queue.front() << std::endl;
    queue.push(6);
    std::cout << queue.back() << std::endl;
    queue.pop();
    std::cout << queue.size() << std::endl;
    std::cout << std::boolalpha << queue.empty() << std::endl;
    std::cout << std::boolalpha << std::find(queue.begin(), queue.end(), 3) != queue.end() << std::endl;
    queue.pop();
    queue.pop();
    queue.pop();
    queue.pop();
    queue.pop();
    std::cout << queue.size() << std::endl;
    return 0;
}
```

</compare>

#### Queue Output C++ {switcher-key="C++"}

```c++
1
10
6
5
false
true
0
```

### Queue 1 Python {switcher-key="Python"}

<compare first-title="Pseudocode" second-title="Python">

```Python
# Declaration
queueName = [value1, value2, value3, ...]

# Initialization
queueName = [value1, value2, value3, ...]

# Accessing an element
queueName[index]

# Assigning a value to an element
queueName[index] = value

# Adding an element
queueName.append(value)

# Removing an element
queueName.pop(0)

# Getting the size of the queue
len(queueName)

# Checking if the queue is empty
len(queueName) == 0

# Checking if the queue contains a value
value in queueName

# Clearing the queue
queueName.clear()
```

```Python
queue = [1, 2, 3, 4, 5]
print(queue[0])
queue[0] = 10
print(queue[0])
queue.append(6)
print(queue[5])
queue.pop(0)
print(len(queue))
print(len(queue) == 0)
print(3 in queue)
queue.clear()
print(len(queue))
```

</compare>

#### Queue 1 Output Python {switcher-key="Python"}

```Python
1
10
6
5
False
True
0
```

### Queue Java {switcher-key="Java"}

<compare first-title="Pseudocode" second-title="Java">

```java
// Declaration
queueType queueName = new queueType();

// Initialization
queueType queueName = {value1, value2, value3, ...};

// Accessing an element
queueName.get(index);

// Assigning a value to an element
queueName.set(index, value);

// Adding an element
queueName.add(value);

// Removing an element
queueName.remove(index);

// Getting the size of the queue
queueName.size();

// Checking if the queue is empty
queueName.isEmpty();

// Checking if the queue contains a value
queueName.contains(value);

// Clearing the queue
queueName.clear();
```

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<Integer> queue = new LinkedList<Integer>();
        queue.add(1);
        queue.add(2);
        queue.add(3);
        queue.add(4);
        queue.add(5);
        System.out.println(queue.get(0));
        queue.set(0, 10);
        System.out.println(queue.get(0));
        queue.add(6);
        System.out.println(queue.get(5));
        queue.remove(0);
        System.out.println(queue.size());
        System.out.println(queue.isEmpty());
        System.out.println(queue.contains(3));
        queue.clear();
        System.out.println(queue.size());
    }
}
```

</compare>

#### Queue Output Java {switcher-key="Java"}

```java
1
10
6
5
false
true
0
```

### Queue Go {switcher-key="Go"}

<compare first-title="Pseudocode" second-title="Go">

```go
// Declaration
var queueName []queueType

// Initialization
queueName := []queueType{value1, value2, value3, ...}

// Accessing an element
queueName[index]

// Assigning a value to an element
queueName[index] = value

// Adding an element
queueName = append(queueName, value)

// Removing an element
queueName = queueName[1:]

// Getting the size of the queue
len(queueName)

// Checking if the queue is empty
len(queueName) == 0

// Checking if the queue contains a value
value in queueName

// Clearing the queue
queueName = nil
```

```go
package main

import "fmt"

func main() {
    queue := []int{1, 2, 3, 4, 5}
    fmt.Println(queue[0])
    queue[0] = 10
    fmt.Println(queue[0])
    queue = append(queue, 6)
    fmt.Println(queue[5])
    queue = queue[1:]
    fmt.Println(len(queue))
    fmt.Println(len(queue) == 0)
    fmt.Println(3 in queue)
    queue = nil
    fmt.Println(len(queue))
}
```

</compare>

#### Queue Output Go {switcher-key="Go"}

```go
1
10
6
5
false
true
0
```

## Set : Declaration, Initialization, and further functionality

### What is a set?

A set is a collection of elements that are not ordered sequentially. The order of the elements is determined by the relationship between the elements. The elements in a set can be accessed one at a time, in a specific order. Sets are used to store, retrieve, manipulate, and communicate aggregate data. Typically, they represent data items that form a natural group, such as a poker hand (a collection of cards), a mail folder (a collection of letters), or a telephone directory (a mapping of names to phone numbers).

### Set Pseudocode {switcher-key="Pseudocode"}

```text

// Declaration
setName : setType

// Initialization
setName : setType = {value1, value2, value3, ...}

// Accessing an element
setName[index]

// Assigning a value to an element
setName[index] = value

// Adding an element
setName.add(value)

// Removing an element
setName.remove(value)

// Getting the size of the set
setName.size()

// Checking if the set is empty
setName.isEmpty()

// Checking if the set contains a value
setName.contains(value)

// Clearing the set
setName.clear()

```

### Set 1 C++ {switcher-key="C++"}

<compare first-title="Pseudocode" second-title="C++">

```c++
// Declaration
setType setName;

// Initialization
setType setName = {value1, value2, value3, ...};

// Accessing an element
setName[index];

// Assigning a value to an element
setName[index] = value;

// Adding an element
setName.insert(value);

// Removing an element
setName.erase(value);

// Getting the size of the set
setName.size();

// Checking if the set is empty
setName.empty();

// Checking if the set contains a value
std::find(setName.begin(), setName.end(), value) != setName.end();

// Clearing the set
setName.clear();
```

```c++
#include <iostream>
#include <set>
#include <algorithm>

int main() {
    std::set<int> set = {1, 2, 3, 4, 5};
    std::cout << *set.begin() << std::endl;
    *set.begin() = 10;
    std::cout << *set.begin() << std::endl;
    set.insert(6);
    std::cout << *set.find(6) << std::endl;
    set.erase(6);
    std::cout << set.size() << std::endl;
    std::cout << std::boolalpha << set.empty() << std::endl;
    std::cout << std::boolalpha << std::find(set.begin(), set.end(), 3) != set.end() << std::endl;
    set.clear();
    std::cout << set.size() << std::endl;
    return 0;
}
```

</compare>

#### Set Output C++ {switcher-key="C++"}

```c++
1
10
6
5
false
true
0
```

### Set Python {switcher-key="Python"}

<compare first-title="Pseudocode" second-title="Python">

```Python
# Declaration
setName = {value1, value2, value3, ...}

# Initialization
setName = {value1, value2, value3, ...}

# Accessing an element
value in setName

# Assigning a value to an element
setName.add(value)

# Adding an element
setName.add(value)

# Removing an element
setName.remove(value)

# Getting the size of the set
len(setName)

# Checking if the set is empty
len(setName) == 0

# Checking if the set contains a value
value in setName

# Clearing the set
setName.clear()
```

```Python
set = {1, 2, 3, 4, 5}
print(1 in set)
set.add(6)
print(6 in set)
set.remove(6)
print(len(set))
print(len(set) == 0)
print(3 in set)
set.clear()
print(len(set))
```

</compare>

#### Set Output Python {switcher-key="Python"}

```Python
True
True
5
False
True
0
```

### Set Java {switcher-key="Java"}

<compare first-title="Pseudocode" second-title="Java">

```java
// Declaration
setType setName = new setType();

// Initialization
setType setName = {value1, value2, value3, ...};

// Accessing an element
setName.get(index);

// Assigning a value to an element
setName.set(index, value);

// Adding an element
setName.add(value);

// Removing an element
setName.remove(value);

// Getting the size of the set
setName.size();

// Checking if the set is empty
setName.isEmpty();

// Checking if the set contains a value
setName.contains(value);

// Clearing the set
setName.clear();
```

```java
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        HashSet<Integer> set = new HashSet<Integer>();
        set.add(1);
        set.add(2);
        set.add(3);
        set.add(4);
        set.add(5);
        System.out.println(set.contains(1));
        set.add(6);
        System.out.println(set.contains(6));
        set.remove(6);
        System.out.println(set.size());
        System.out.println(set.isEmpty());
        System.out.println(set.contains(3));
        set.clear();
        System.out.println(set.size());
    }
}
```

</compare>

#### Set Output Java {switcher-key="Java"}

```java
true
true
5
false
true
0
```

### Set Go {switcher-key="Go"}

<compare first-title="Pseudocode" second-title="Go">

```go
// Declaration
var setName []setType

// Initialization
setName := []setType{value1, value2, value3, ...}

// Accessing an element
value in setName

// Assigning a value to an element
setName = append(setName, value)

// Adding an element
setName = append(setName, value)

// Removing an element
for i, v := range setName {
    if v == value {
        setName = append(setName[:i], setName[i+1:]...)
        break
    }
}

// Getting the size of the set
len(setName)

// Checking if the set is empty
len(setName) == 0

// Checking if the set contains a value
value in setName
    
// Clearing the set
setName = nil
```

```go
package main

import "fmt"

func main() {
    set := []int{1, 2, 3, 4, 5}
    fmt.Println(1 in set)
    set = append(set, 6)
    fmt.Println(6 in set)
    for i, v := range set {
        if v == 6 {
            set = append(set[:i], set[i+1:]...)
            break
        }
    }
    fmt.Println(len(set))
    fmt.Println(len(set) == 0)
    fmt.Println(3 in set)
    set = nil
    fmt.Println(len(set))
}
```

</compare>

#### Set Output Go {switcher-key="Go"}

```go
true
true
5
false
true
0
```

## Map : Declaration, Initialization, and further functionality

### What is a map?

A map is a collection of elements that are not ordered sequentially. The order of the elements is determined by the relationship between the elements. The elements in a map can be accessed one at a time, in a specific order. Maps are used to store, retrieve, manipulate, and communicate aggregate data. Typically, they represent data items that form a natural group, such as a poker hand (a collection of cards), a mail folder (a collection of letters), or a telephone directory (a mapping of names to phone numbers).

### Map 1 Pseudocode {switcher-key="Pseudocode"}

```text

// Declaration
mapName : mapType

// Initialization
mapName : mapType = {key1:value1, key2:value2, key3:value3, ...}

// Accessing an element
mapName[key]

// Assigning a value to an element
mapName[key] = value

// Adding an element
mapName[key] = value

// Removing an element
mapName.remove(key)

// Getting the size of the map
mapName.size()

// Checking if the map is empty
mapName.isEmpty()

// Checking if the map contains a key
mapName.containsKey(key)

// Checking if the map contains a value
mapName.containsValue(value)

// Clearing the map
mapName.clear()

```

### Map 1 C++ {switcher-key="C++"}

<compare first-title="Pseudocode" second-title="C++">

```c++
// Declaration
mapType mapName;

// Initialization
mapType mapName = {key1:value1, key2:value2, key3:value3, ...};

// Accessing an element
mapName[key];

// Assigning a value to an element
mapName[key] = value;

// Adding an element
mapName[key] = value;

// Removing an element
mapName.erase(key);

// Getting the size of the map
mapName.size();

// Checking if the map is empty
mapName.empty();

// Checking if the map contains a key
mapName.find(key) != mapName.end();

// Checking if the map contains a value
std::find(mapName.begin(), mapName.end(), value) != mapName.end();

// Clearing the map
mapName.clear();
```

```c++
#include <iostream>
#include <map>
#include <algorithm>

int main() {
    std::map<int, int> map = {{1, 1}, {2, 2}, {3, 3}, {4, 4}, {5, 5}};
    std::cout << map[1] << std::endl;
    map[1] = 10;
    std::cout << map[1] << std::endl;
    map[6] = 6;
    std::cout << map[6] << std::endl;
    map.erase(6);
    std::cout << map.size() << std::endl;
    std::cout << std::boolalpha << map.empty() << std::endl;
    std::cout << std::boolalpha << map.find(3) != map.end() << std::endl;
    std::cout << std::boolalpha << std::find(map.begin(), map.end(), 3) != map.end() << std::endl;
    map.clear();
    std::cout << map.size() << std::endl;
    return 0;
}
```

</compare>

#### Map Output C++ {switcher-key="C++"}

```c++
1
10
6
5
false
true
true
true
0
```

### Map Python {switcher-key="Python"}

<compare first-title="Pseudocode" second-title="Python">

```Python
# Declaration
mapName = {key1:value1, key2:value2, key3:value3, ...}

# Initialization
mapName = {key1:value1, key2:value2, key3:value3, ...}

# Accessing an element
mapName[key]

# Assigning a value to an element
mapName[key] = value

# Adding an element
mapName[key] = value

# Removing an element
del mapName[key]

# Getting the size of the map
len(mapName)

# Checking if the map is empty
len(mapName) == 0

# Checking if the map contains a key
key in mapName

# Checking if the map contains a value
value in mapName.values()

# Clearing the map
mapName.clear()
```

```Python
map = {1:1, 2:2, 3:3, 4:4, 5:5}
print(map[1])
map[1] = 10
print(map[1])
map[6] = 6
print(map[6])
del map[6]
print(len(map))
print(len(map) == 0)
print(3 in map)
print(3 in map.values())
map.clear()
print(len(map))
```

</compare>

#### Map Output Python {switcher-key="Python"}

```Python
1
10
6
5
False
True
True
True
0
```

### Map Java {switcher-key="Java"}

<compare first-title="Pseudocode" second-title="Java">

```java
// Declaration
mapType mapName = new mapType();

// Initialization
mapType mapName = {key1:value1, key2:value2, key3:value3, ...};

// Accessing an element
mapName.get(key);

// Assigning a value to an element
mapName.set(key, value);

// Adding an element
mapName.add(key, value);

// Removing an element
mapName.remove(key);

// Getting the size of the map
mapName.size();

// Checking if the map is empty
mapName.isEmpty();

// Checking if the map contains a key
mapName.containsKey(key);

// Checking if the map contains a value
mapName.containsValue(value);

// Clearing the map
mapName.clear();
```

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, Integer> map = new HashMap<Integer, Integer>();
        map.put(1, 1);
        map.put(2, 2);
        map.put(3, 3);
        map.put(4, 4);
        map.put(5, 5);
        System.out.println(map.get(1));
        map.put(1, 10);
        System.out.println(map.get(1));
        map.put(6, 6);
        System.out.println(map.get(6));
        map.remove(6);
        System.out.println(map.size());
        System.out.println(map.isEmpty());
        System.out.println(map.containsKey(3));
        System.out.println(map.containsValue(3));
        map.clear();
        System.out.println(map.size());
    }
}
```

</compare>

#### Map Output Java {switcher-key="Java"}

```java
1
10
6
5
false
true
true
true
0
```

### Map Go {switcher-key="Go"}

<compare first-title="Pseudocode" second-title="Go">

```go
// Declaration
var mapName map[mapKeyType]mapValueType

// Initialization
mapName := map[mapKeyType]mapValueType{key1:value1, key2:value2, key3:value3, ...}

// Accessing an element
mapName[key]

// Assigning a value to an element
mapName[key] = value

// Adding an element
mapName[key] = value

// Removing an element
delete(mapName, key)

// Getting the size of the map
len(mapName)

// Checking if the map is empty
len(mapName) == 0

// Checking if the map contains a key
key in mapName

// Checking if the map contains a value
value in mapName

// Clearing the map
mapName = nil
```

```go
package main

import "fmt"

func main() {
    mapName := map[int]int{1:1, 2:2, 3:3, 4:4, 5:5}
    fmt.Println(mapName[1])
    mapName[1] = 10
    fmt.Println(mapName[1])
    mapName[6] = 6
    fmt.Println(mapName[6])
    delete(mapName, 6)
    fmt.Println(len(mapName))
    fmt.Println(len(mapName) == 0)
    fmt.Println(3 in mapName)
    fmt.Println(3 in mapName.values())
    mapName = nil
    fmt.Println(len(mapName))
}
```

</compare>

#### Map Output Go {switcher-key="Go"}

```go
1
10
6
5
false
true
true
true
0
```







































