---
switcher-label: Language
---

<show-structure for="chapter,procedure" depth="1"/>

# Functions

![Functions](functions.jpeg)
{ centered=true }

## Overview

<note>
<b>Definition &amp; Use</b>

A function is a block of code that performs a specific task. A function is defined once and can be called (i.e., executed) any number of times. A function can be called from within another function.
</note>

<table>
<tr>
<td>Pros</td><td>Cons</td>
</tr>
<tr>
<td>
<deflist collapsible="true">
<def title="Modularity">
Functions break down complex tasks into smaller, manageable pieces.
</def>
<def title="Reusability">
Functions can be reused in different parts of a program.
</def>
<def title="Readability">
Well-named functions make code easier to understand.
</def>
<def title="Debugging">
Isolating functions helps in pinpointing and fixing issues.
</def>
<def title="Scoping">
Functions define variable scopes, reducing naming conflicts.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true">
<def title="Overhead">
Functions may introduce a slight overhead in terms of memory and performance.
</def>
<def title="Complexity">
Overuse of functions can lead to code that’s hard to follow.
</def>
<def title="Maintainability">
Poorly designed functions can hinder rather than help.
</def>
</deflist>
</td>
</tr>
</table>

## Syntax

### Function Definition

A function is defined as follows:

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

```text
function name
    // Statements
end function
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

```c++
return_type name(parameter_list)
{
    // Statements
}
```

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python

def name(parameter_list):
    # Statements
```

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java
return_type name(parameter_list)
{
    // Statements
}
```

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```go
func name(parameter_list) return_type {
    // Statements
}
```

</procedure>


### Definition with Calls

#### What is a function call?

A function call is a statement that executes a function. A function call is defined in the function definition. A function call is executed in the function call.

The following example shows a function definition and calls:

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

```text
function main
    // Statements
    call function1
    call function2
end function

function function1
    // Statements
end function

function function2
    // Statements
end function
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

```c++
#include <iostream>

using namespace std;

void function1();
void function2();

int main()
{
    cout << "main" << endl;
    function1();
    function2();
    return 0;
}

void function1()
{
    cout << "function1" << endl;
}

void function2()
{
    cout << "function2" << endl;
}
```

<br/>

```c++ 
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python
def function1():
    print("function1")

def function2():
    print("function2")

def main():
    print("main")
    function1()
    function2()

main()
```

<br/>

```python
# Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java
public class Main {

    public static void main(String[] args) {
        System.out.println("main");
        function1();
        function2();
    }

    public static void function1() {
        System.out.println("function1");
    }

    public static void function2() {
        System.out.println("function2");
    }
}
```

<br/>

```java
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```go
package main

import "fmt"

func function1() {
    fmt.Println("function1")
}

func function2() {
    fmt.Println("function2")
}

func main() {
    fmt.Println("main")
    function1()
    function2()
}
```

<br/>

```go
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

### Function Parameters

A function can have zero or more parameters. A parameter is a variable that is passed to a function. A parameter is defined in the function definition. A parameter is passed to a function in the function call.

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

```text
function name(parameter_list)
    // Statements
end function
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

```c++
return_type name(parameter_list)
{
    // Statements
}
```

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python

def name(parameter_list):
    # Statements
```

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java

return_type name(parameter_list)
{
    // Statements
}
```

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```go
func name(parameter_list) return_type {
    // Statements
}
```

</procedure>

### Example

The following example shows a function definition and calls:

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

```text
function main
    // Statements
    call function1
    call function2
end function

function function1
    // Statements
end function

function function2
    // Statements
end function
```

<br/>

```text
main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

```c++
#include <iostream>

using namespace std;

void function1();
void function2();

int main()
{
    cout << "main" << endl;
    function1();
    function2();
    return 0;
}

void function1()
{
    cout << "function1" << endl;
}

void function2()
{
    cout << "function2" << endl;
}
```

<br/>

```c++
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python

def function1():
    print("function1")

def function2():
    print("function2")

def main():
    print("main")
    function1()
    function2()

main()
```

<br/>

```python
# Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java

public class Main {

    public static void main(String[] args) {
        System.out.println("main");
        function1();
        function2();
    }

    public static void function1() {
        System.out.println("function1");
    }

    public static void function2() {
        System.out.println("function2");
    }
}
```

<br/>

```java
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```go
package main

import "fmt"

func function1() {
    fmt.Println("function1")
}

func function2() {
    fmt.Println("function2")
}

func main() {
    fmt.Println("main")
    function1()
    function2()
}
```

<br/>

```go
main
function1
function2
```
{ collapsible="true" }

</procedure>


### Function Return Values

A function can return zero or one value. A return value is a value that is returned from a function. A return value is defined in the function definition. A return value is returned from a function in the function call.

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

```text

function name(parameter_list)
    // Statements
    return value
end function
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

```c++
return_type name(parameter_list)
{
    // Statements
    return value;
}
```

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python


```python

def name(parameter_list):
    # Statements
    return value
```

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java

return_type name(parameter_list)
{
    // Statements
    return value;
}
```

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```go

func name(parameter_list) return_type {
    // Statements
    return value
}
```

</procedure>


## Built-in Functions

### What is a built-in function?

<note>
<b>Definition &amp; Use</b>

A built-in function is a function that is provided by a programming language. A built-in function is defined in the language's standard library. A built-in function is called by its name.
</note>

The following example shows a built-in function:

<procedure switcher-key="Pseudocode">

```text
function main
    // Statements
    call print
end function
```

</procedure>

<procedure switcher-key="C++">

```c++
#include <iostream>

using namespace std;

int main()
{
    cout << "main" << endl;
}
```

<br/>

```c++
// Output

main
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">

```python
def main():
    print("main")

main()
```

<br/>

```python
# Output

main
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">

```java
public class Main {

    public static void main(String[] args) {
        System.out.println("main");
    }
}
```

<br/>

```java
// Output
    
main
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">

```go
package main
import "fmt"

func main() {
    fmt.Println("main")
}
```

<br/>

```go
// Output

main
```
{ collapsible="true" }

</procedure>

### User-Defined Functions

#### What is a user-defined function?

<note>
<b>Definition &amp; Use</b>

A user-defined function is a function that is defined by a user. A user-defined function is defined in the program. A user-defined function is called by its name.
</note>

The following example shows a user-defined function:

<procedure switcher-key="Pseudocode">

```text
function main
    // Statements
    call function1
    call function2
end function

function function1
    // Statements
end function

function function2
    // Statements
end function
```

</procedure>

<procedure switcher-key="C++">

```c++
#include <iostream>
using namespace std;

void function1() {
    cout << "function1" << endl;
}

void function2() {
    cout << "function2" << endl;
}

int main() {
    cout << "main" << endl;
    function1();
    function2();
    return 0;
}
```

<br/>

```c++
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">

```python
def function1():
    print("function1")
    
def function2():
    print("function2")
    
def main():
    print("main")
    function1()
    function2()
    
if __name__ == "__main__":
    main()
```

<br/>

```python
# Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">

```java
public class Main {

    public static void function1() {
        System.out.println("function1");
    }

    public static void function2() {
        System.out.println("function2");
    }

    public static void main(String[] args) {
        System.out.println("main");
        function1();
        function2();
    }
}
```

<br/>

```java
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">

```go
package main
import "fmt"

func function1() {
    fmt.Println("function1")
}

func function2() {
    fmt.Println("function2")
}

func main() {
    fmt.Println("main")
    function1()
    function2()
}
```

<br/>

```go
// Output

main
function1
function2
```
{ collapsible="true" }

</procedure>


## Function Overloading

### What is function overloading?

<note>
<b>Definition &amp; Use</b>

Function overloading is a feature that allows a function to have the same name but different parameters. Function overloading is used to create multiple functions with the same name but different parameter lists. Function overloading is used to create functions that perform similar tasks but with different inputs.

Function overloading is not supported in Go.
</note>

The following example shows function overloading:

<procedure switcher-key="Pseudocode">

```text
function name(parameter_list1)
    // Statements
end function

function name(parameter_list2)
    // Statements
end function
```

</procedure>

<procedure switcher-key="C++">

```c++
#include <iostream>
using namespace std;

void print(int i) {
    cout << "Printing int: " << i << endl;
}

void print(double f) {
    cout << "Printing float: " << f << endl;
}

void print(char* c) {
    cout << "Printing character: " << c << endl;
}

int main() {
    print(10);
    print(10.10);
    print("ten");
    return 0;
}
```

<br/>

```c++
// Output

Printing int: 10
Printing float: 10.1
Printing character: ten
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">

```python
def print_int(i):
    print("Printing int:", i)

def print_float(f):
    print("Printing float:", f)

def print_char(c):
    print("Printing character:", c)

print_int(10)
print_float(10.10)
print_char("ten")
```

<br/>

```python
# Output

Printing int: 10
Printing float: 10.1
Printing character: ten
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">

```java
public class Main {

    public static void print(int i) {
        System.out.println("Printing int: " + i);
    }

    public static void print(double f) {
        System.out.println("Printing float: " + f);
    }

    public static void print(String c) {
        System.out.println("Printing character: " + c);
    }

    public static void main(String[] args) {
        print(10);
        print(10.10);
        print("ten");
    }
}
```

<br/>

```java
// Output

Printing int: 10
Printing float: 10.1
Printing character: ten
```
{ collapsible="true" }

</procedure>


