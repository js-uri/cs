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

##### Definition Pseudocode {switcher-key="Pseudocode"}

```text
function name
    // Statements
end function
```

##### Definition C++ {switcher-key="C++"}

```c++
return_type name(parameter_list)
{
    // Statements
}
```

##### Definition Python {switcher-key="Python"}

```python

def name(parameter_list):
    # Statements
```

#### Definition Java {switcher-key="Java"}

```java
return_type name(parameter_list)
{
    // Statements
}
```

#### Definition Go {switcher-key="Go"}

```go
func name(parameter_list) return_type {
    // Statements
}
```


### Definition with Calls

#### What is a function call?

A function call is a statement that executes a function. A function call is defined in the function definition. A function call is executed in the function call.

The following example shows a function definition and calls:

#### Function Calls Pseudocode {switcher-key="Pseudocode"}

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

#### Function Calls C++ {switcher-key="C++"}

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

#### Output 1 C++ {switcher-key="C++"}

```c++ 
main
function1
function2
```

#### Function Calls Python {switcher-key="Python"}

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

#### Output 1 Python {switcher-key="Python"}

```python
main
function1
function2
```

#### Function Calls Java {switcher-key="Java"}

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

#### Output 1 Java {switcher-key="Java"}

```java
main
function1
function2
```

#### Function Calls Go {switcher-key="Go"}

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

#### Output 1 Go {switcher-key="Go"}

```go
main
function1
function2
```

### Function Parameters

A function can have zero or more parameters. A parameter is a variable that is passed to a function. A parameter is defined in the function definition. A parameter is passed to a function in the function call.

#### Function Parameters 1 Pseudocode {switcher-key="Pseudocode"}

```text
function name(parameter_list)
    // Statements
end function
```

#### Function Parameters 1 C++ {switcher-key="C++"}

```c++
return_type name(parameter_list)
{
    // Statements
}
```

#### Function Parameters 1 Python {switcher-key="Python"}

```python

def name(parameter_list):
    # Statements
```

#### Function Parameters 1 Java {switcher-key="Java"}

```java

return_type name(parameter_list)
{
    // Statements
}
```

#### Function Parameters 1 Go {switcher-key="Go"}

```go
func name(parameter_list) return_type {
    // Statements
}
```

### Example

The following example shows a function definition and calls:

#### Function Parameters 2 Pseudocode {switcher-key="Pseudocode"}

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

#### Output 2 Pseudocode {switcher-key="Pseudocode"}

```text
main
function1
function2
```

#### Function Parameters 2 C++ {switcher-key="C++"}

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

#### Output 2 C++ {switcher-key="C++"}

```c++
main
function1
function2
```


#### Function Parameters 2 Python {switcher-key="Python"}

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

#### Output 2 Python {switcher-key="Python"}

```python
main
function1
function2
```


#### Function Parameters 2 Java {switcher-key="Java"}

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

#### Output 2 Java {switcher-key="Java"}

```java
main
function1
function2
```


#### Function Parameters 2 Go {switcher-key="Go"}

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

#### Output 2 Go {switcher-key="Go"}

```go
main
function1
function2
```


### Function Return Values

A function can return zero or one value. A return value is a value that is returned from a function. A return value is defined in the function definition. A return value is returned from a function in the function call.

#### Function Returns Pseudocode {switcher-key="Pseudocode"}

```text

function name(parameter_list)
    // Statements
    return value
end function
```

#### Function Returns C++ {switcher-key="C++"}

```c++
return_type name(parameter_list)
{
    // Statements
    return value;
}
```

#### Function Returns Python {switcher-key="Python"}

```python

def name(parameter_list):
    # Statements
    return value
```

#### Function Returns Java {switcher-key="Java"}

```java

return_type name(parameter_list)
{
    // Statements
    return value;
}
```

#### Function Returns Go {switcher-key="Go"}

```go

func name(parameter_list) return_type {
    // Statements
    return value
}
```
