---
switcher-label: Language
---

# Data Types

![Data Types](https://cdn.mindmajix.com/blog/images/java-03_0719.png)
{ width="900" }


## Overview

<note>
<p>Definition</p>
<p>Data types in programming languages represent the type of data that can be stored in variables. They define the size, memory allocation, and operations that can be performed on the data. Common data types include integers, floating-point numbers, characters, strings, booleans, and more complex types like arrays and structures.</p>
</note>

<tip>
<p>Use Cases</p>
<p>Data types are essential for defining variables and data structures to hold different kinds of information in a program. They help enforce constraints on data and enable efficient memory management and manipulation.</p>
</tip>

<warning>
<table>
<tr>
<th>Pros</th><th>Cons</th>
</tr>
<tr>
<td>
<deflist collapsible="true">
<def title="Type Safety">Data types help catch type-related errors at compile-time, enhancing code reliability.</def>
<def title="Memory Optimization">Choosing appropriate data types can optimize memory usage.</def>
<def title="Performance">Properly selected data types improve the execution speed of programs.</def>
<def title="Code Clarity">Explicit data types make code more readable and self-documenting.</def>
</deflist>
</td>
<td>
<deflist collapsible="true">
<def title="Type Constraints">Incorrectly chosen data types can lead to unnecessary restrictions or potential errors.</def>
<def title="Memory Overhead">In certain situations, using larger data types can lead to memory waste.</def>
<def title="Conversion Overhead">Implicit type conversions can lead to performance overhead in some cases.</def>
</deflist>
</td>
</tr>
</table>
</warning>

## Types of Data Types

<table>
<tr>
<td>Primitive Data Types</td><td>Composite Data Types</td>
</tr>
<tr>
<td>
<note>
<p>Definition</p>
<p>Primitive data types are the most basic data types in a programming language. They are built-in and supported by the language itself. They are also called intrinsic data types.</p>
</note>

<tip>
<p>Use Cases</p>
<p>Primitive data types are used to store simple values like numbers, characters, and booleans.</p>
</tip>

<tip>
<p>Examples</p>
<p>Examples of primitive data types include integers, floating-point numbers, characters, booleans, and pointers.</p>
</tip>
</td>
<td>
<note>
<p>Definition</p>
<p>Composite data types are data types that are composed of other data types. They are also called non-primitive data types.</p>
</note>

<tip>
<p>Use Cases</p>
<p>Composite data types are used to store more complex data like arrays, structures, and classes.</p>
</tip>

<tip>
<p>Examples</p>
<p>Examples of composite data types include arrays, structures, and classes.</p>
</tip>
</td>
</tr>
<tr>
<th colspan="2">
Common Data Types
</th>
</tr>
<tr>
<td colspan="2">
<deflist collapsible="true">
<def title="Integers">
<note>
<p>Definition</p>
<p>Integers are whole numbers that can be positive, negative, or zero. They are represented by the `int` data type in most programming languages.</p>
</note>

<tip>
<p>Use Cases</p>
<p>Integers are used to store whole numbers like the number of students in a class, the number of items in a shopping cart, and the number of days in a week.</p>
</tip>

<tip>
<p>Examples</p>

Examples of integers include `0`, `1`, `-1`, `2`, `-2`, `3`, `-3`, and so on.

<code-block lang="C++" switcher-key="C++">
int a = 5;
int b = -5;
</code-block>

<code-block lang="Python" switcher-key="Python">
a = 5
b = -5
</code-block>

<code-block lang="Java" switcher-key="Java">
int a = 5;
int b = -5;
</code-block>

<code-block lang="Go" switcher-key="Go">
a := 5
b := -5
</code-block>

</tip>

</def>
<def title="Floating-Point Numbers">
<note>
<p>Definition</p>

Floating-point numbers are numbers that have a fractional part. They are represented by the `float` data type in most programming languages.
</note>

<tip>
<p>Use Cases</p>
<p>Floating-point numbers are used to store numbers with a fractional part like the price of an item, the weight of a person, and the height of a building.</p>
</tip>

<tip>
<p>Examples</p>

Examples of floating-point numbers include `0.0`, `1.0`, `-1.0`, `2.0`, `-2.0`, `3.0`, `-3.0`, and so on.

<code-block lang="C++" switcher-key="C++">
float a = 5.5;
float b = -5.5;
</code-block>

<code-block lang="Python" switcher-key="Python">
a = 5.5
b = -5.5
</code-block>

<code-block lang="Java" switcher-key="Java">
float a = 5.5;
float b = -5.5;
</code-block>

<code-block lang="Go" switcher-key="Go">
a := 5.5
b := -5.5
</code-block>

</tip>
</def>
<def title="Characters">
<note>
<p>Definition</p>
<p>Characters are single letters, digits, or symbols. They are represented by the `char` data type in most programming languages.</p>
</note>

<tip>
<p>Use Cases</p>
<p>Characters are used to store single letters, digits, or symbols like the first letter of a name, the first digit of a phone number, and the currency symbol of a country.</p>
</tip>

<tip>
<p>Examples</p>

Examples of characters include `a`, `b`, `c`, `1`, `2`, `3`, `@`, `#`, `$`, and so on.

<code-block lang="C++" switcher-key="C++">
char a = 'A';
char b = 'B';
</code-block>

<code-block lang="Python" switcher-key="Python">
# Note : Python does not have a separate char data type
a = 'A'
b = 'B'
</code-block>

<code-block lang="Java" switcher-key="Java">
char a = 'A';
char b = 'B';
</code-block>

<code-block lang="Go" switcher-key="Go">
a := 'A'
b := 'B'
</code-block>

</tip>
</def>
<def title="Strings">
<note>
<p>Definition</p>

Strings are sequences of characters. They are represented by the `string` data type in most programming languages.
</note>

<tip>
<p>Use Cases</p>
<p>Strings are used to store sequences of characters like names, addresses, and messages.</p>
</tip>

<tip>
<p>Examples</p>

Examples of strings include `Hello`, `World`, `John`, `Doe`, `123`, `abc`, `@#$`, and so on.

<code-block lang="C++" switcher-key="C++">
string a = "Hello";
string b = "World";
</code-block>

<code-block lang="Python" switcher-key="Python">
a = "Hello"
b = "World"
</code-block>

<code-block lang="Java" switcher-key="Java">
String a = "Hello";
String b = "World";
</code-block>

<code-block lang="Go" switcher-key="Go">
a := "Hello"
b := "World"
</code-block>

</tip>
</def>
<def title="Booleans">
<note>
<p>Definition</p>

Booleans are values that can be either `true` or `false`. They are represented by the `bool` data type in most programming languages.
</note>

<tip>
<p>Use Cases</p>

Booleans are used to store values that can be either `true` or `false` like the result of a comparison or the state of a switch.
</tip>

<tip>
<p>Examples</p>

Examples of booleans include `true` and `false`.

<code-block lang="C++" switcher-key="C++">
bool a = true;
bool b = false;
</code-block>

<code-block lang="Python" switcher-key="Python">
a = True
b = False
</code-block>

<code-block lang="Java" switcher-key="Java">
boolean a = true;
boolean b = false;
</code-block>

<code-block lang="Go" switcher-key="Go">
a := true
b := false
</code-block>

</tip>
</def>
</deflist>
</td>
</tr>
</table>



## Syntax 

### Pseudocode {switcher-key="Pseudocode"}

<video src="https://youtu.be/p98cayTo1Go?feature=shared" width="900"  mini-player="true" />

#### Sample Pseudocode

```text
input length, width
area = length * width
print area
```

#### Output Pseudocode

```text
area
```

### C++   {switcher-key="C++"}

<video src="https://youtu.be/4fJBrditnJU?feature=shared" width="900" mini-player="true" />

#### Sample C++

```c++
// Declare variables
int length, width, area;

// Take input
cin >> length >> width;

// Calculate area
area = length * width;

// Print result
cout << area;
```

#### Output C++

The code samples above calculate the `area` of a rectangle given its length and width. The user enters the `length` and `width`, and the program performs the necessary calculations.

Assume the user enters `length = 5` and `width = 7` for all the examples.

```text
Area of the rectangle: 35
```

### Python   {switcher-key="Python"}

<video src="https://youtu.be/7zlRqvbuCGU?feature=shared" width="900" mini-player="true" />

#### Sample Python

```python
# Take input
length = int(input())
width = int(input())

# Calculate area
area = length * width

# Print result
print(area)
```

#### Output Python

The code samples above calculate the `area` of a rectangle given its length and width. The user enters the `length` and `width`, and the program performs the necessary calculations.

Assume the user enters `length = 5` and `width = 7` for all the examples.

```text
Area of the rectangle: 35.0
```

### Java   {switcher-key="Java"}

<video src="https://youtu.be/Le25I331_yU?feature=shared" width="900" mini-player="true" />

#### Sample Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double length, width;
        System.out.print("Enter length: ");
        length = scanner.nextDouble();
        System.out.print("Enter width: ");
        width = scanner.nextDouble();

        double area = length * width;
        System.out.println("Area of the rectangle: " + area);
    }
}
```

#### Output Java

The code samples above calculate the `area` of a rectangle given its length and width. The user enters the `length` and `width`, and the program performs the necessary calculations.

Assume the user enters `length = 5` and `width = 7` for all the examples.

```text
Area of the rectangle: 35.0
```

### Go   {switcher-key="Go"}

<video src="https://youtu.be/pM0-CMysa_M?feature=shared" width="900" mini-player="true" />

#### Sample Go

```go
package main

import (
    "fmt"
)

func main() {
    var length, width float64

    fmt.Print("Enter length: ")
    fmt.Scan(&length)

    fmt.Print("Enter width: ")
    fmt.Scan(&width)

    area := length * width
    fmt.Println("Area of the rectangle:", area)
}
```

#### Output Go

The code samples above calculate the `area` of a rectangle given its length and width. The user enters the `length` and `width`, and the program performs the necessary calculations.

Assume the user enters `length = 5` and `width = 7` for all the examples.

```text
Area of the rectangle: 35
```


[//]: # (### Rust   {switcher-key="Rust"})

[//]: # ()
[//]: # (<video src="https://youtu.be/t047Hseyj_k?feature=shared" width="900" mini-player="true" />)

[//]: # ()
[//]: # (```rust)

[//]: # (use std::io;)

[//]: # ()
[//]: # (fn main&#40;&#41; {)

[//]: # (    let mut input = String::new&#40;&#41;;)

[//]: # (    println!&#40;"Enter length: "&#41;;)

[//]: # (    io::stdin&#40;&#41;.read_line&#40;&mut input&#41;.expect&#40;"Failed to read line"&#41;;)

[//]: # (    let length: f64 = input.trim&#40;&#41;.parse&#40;&#41;.expect&#40;"Please enter a valid number"&#41;;)

[//]: # ()
[//]: # (    input.clear&#40;&#41;;)

[//]: # (    println!&#40;"Enter width: "&#41;;)

[//]: # (    io::stdin&#40;&#41;.read_line&#40;&mut input&#41;.expect&#40;"Failed to read line"&#41;;)

[//]: # (    let width: f64 = input.trim&#40;&#41;.parse&#40;&#41;.expect&#40;"Please enter a valid number"&#41;;)

[//]: # ()
[//]: # (    let area = length * width;)

[//]: # (    println!&#40;"Area of the rectangle: {}", area&#41;;)

[//]: # (})

[//]: # (```)

[//]: # ()
[//]: # (#### Output Rust)

[//]: # ()
[//]: # (If the user enters `5` and `2` as input, the output will be:)

[//]: # ()
[//]: # (```text)

[//]: # (Area of the rectangle: 35)

[//]: # (```)












