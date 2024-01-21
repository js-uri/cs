---
switcher-label: Language
---

# Expressions

![Expressions](https://media.geeksforgeeks.org/wp-content/uploads/20190801154515/Types-of-Expressions.jpg)

## Overview

<note>
<p>Definition</p>

An expression is a combination of values, variables, operators, and functions that are interpreted and evaluated to produce another value.
</note>

### Characteristics

Expressions are made up of the following components:

<deflist collapsible="true">
<def title="Operators">

Expressions involve operators, which are symbols that represent specific operations. Examples of operators include addition (`+`), subtraction (`-`), multiplication (`*`), division (`/`), and comparison operators (`==`, `!=`, `<`, `>`, etc.).
</def>
<def title="Operands">

These are the values or variables that the operators act upon. For instance, in the expression `5 + x`, the values `5` and `x` are operands.
</def>
<def title="Values">
A value is a piece of data that can be stored in a variable or used in an expression. Values can be numbers, strings, booleans, or other data types.
</def>
<def title="Variables">
A variable is a named storage location that can hold a value. Variables are used to store values that can be used in expressions.
</def>
<def title="Functions">
A function is a block of code that performs a specific task. Functions are used to perform complex operations on values and variables.
</def>
<def title="Precedence">
Expressions follow operator precedence rules, which determine the order in which operators are evaluated. Parentheses can be used to override the default precedence.
</def>
<def title="Evaluation">
The process of evaluating an expression involves substituting values for variables, applying operators, and calculating the final result. The result of evaluating an expression is a single value.
</def>
</deflist>

## Syntax

### Pseudocode {switcher-key="Pseudocode"}

<video src="https://youtu.be/LV8tCxAxm7E?feature=shared" width="900" mini-player="true"/>

#### Sample Pseudocode

```text
1. Input a
2. Input b
3. Input c
4. Input d
5. result = (a + b) * (c - d)
6. Output result
```

#### Output Pseudocode

In each example, the user inputs four values to be stored in variables `a`, `b`, `c`, and `d` the sum of variables `a` & `b` is found the difference of variables `c` & `d` is found the product of the prior sum & difference is found

Assuming user inputs (in order) : `1`, `2`, `3`, `4`

```text
result
```

### C++ {switcher-key="C++"}

<video src="https://youtu.be/cqi060vJuoI?feature=shared" width="900" mini-player="true"/>

#### Sample C++

```c++
#include <iostream>

int main() {
    double a, b, c, d;
    
    std::cout << "Enter the value of a: ";
    std::cin >> a;
    std::cout << "Enter the value of b: ";
    std::cin >> b;
    std::cout << "Enter the value of c: ";
    std::cin >> c;
    std::cout << "Enter the value of d: ";
    std::cin >> d;
    
    double result = (a + b) * (c - d);
    
    std::cout << "Result: " << result << std::endl;
    
    return 0;
}
```

#### Output C++

In each example, the user inputs four values to be stored in variables `a`, `b`, `c`, and `d` the sum of variables `a` & `b` is found the difference of variables `c` & `d` is found the product of the prior sum & difference is found

Assuming user inputs (in order) : `1`, `2`, `3`, `4`

```text
Result: -3
```

### Python {switcher-key="Python"}

<video src="https://youtu.be/LZFpLUKpo1I?feature=shared" width="900" mini-player="true"/>

#### Sample Python

```python
a = float(input("Enter the value of a: "))
b = float(input("Enter the value of b: "))
c = float(input("Enter the value of c: "))
d = float(input("Enter the value of d: "))

result = (a + b) * (c - d)

print("Result:", result)
```

#### Output Python

In each example, the user inputs four values to be stored in variables `a`, `b`, `c`, and `d` the sum of variables `a` & `b` is found the difference of variables `c` & `d` is found the product of the prior sum & difference is found

Assuming user inputs (in order) : `1`, `2`, `3`, `4`

```text
Result: -3.0
```

### Java {switcher-key="Java"}

<video src="https://youtu.be/RA7wkTV6z4k?feature=shared" width="900" mini-player="true"/>

#### Sample Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.print("Enter the value of a: ");
        double a = input.nextDouble();
        System.out.print("Enter the value of b: ");
        double b = input.nextDouble();
        System.out.print("Enter the value of c: ");
        double c = input.nextDouble();
        System.out.print("Enter the value of d: ");
        double d = input.nextDouble();
        
        double result = (a + b) * (c - d);
        
        System.out.println("Result: " + result);
    }
}
```

#### Output Java

In each example, the user inputs four values to be stored in variables `a`, `b`, `c`, and `d` the sum of variables `a` & `b` is found the difference of variables `c` & `d` is found the product of the prior sum & difference is found

Assuming user inputs (in order) : `1`, `2`, `3`, `4`

```text
Result: -3.0
```

### Go {switcher-key="Go"}

<video src="https://youtu.be/VMveb4GqRck?feature=shared" width="900" mini-player="true"/>

#### Sample Go

```go
package main

import (
    "fmt"
)

func main() {
    var a, b, c, d float64

    fmt.Print("Enter the value of a: ")
    fmt.Scan(&a)
    fmt.Print("Enter the value of b: ")
    fmt.Scan(&b)
    fmt.Print("Enter the value of c: ")
    fmt.Scan(&c)
    fmt.Print("Enter the value of d: ")
    fmt.Scan(&d)

    result := (a + b) * (c - d)

    fmt.Printf("Result: %f\n", result)
}
```

#### Output Go

In each example, the user inputs four values to be stored in variables `a`, `b`, `c`, and `d` the sum of variables `a` & `b` is found the difference of variables `c` & `d` is found the product of the prior sum & difference is found

Assuming user inputs (in order) : `1`, `2`, `3`, `4`

```text
Result: -3
```
