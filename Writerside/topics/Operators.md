---
switcher-label: Language
---

# Operators

![Operators](https://i.ytimg.com/vi/1mbgeb4w3wc/maxresdefault.jpg)
{ center=true }

## What are Operators?

Operators are symbols that perform operations on variables and values. For example, the addition operator (`+`) adds two values together, and the assignment operator (`=`) assigns a value to a variable. Operators are used in expressions, which are combinations of values, variables, and operators that are evaluated to produce a single value. For example, the expression `5 + 2` evaluates to `7`. In this case, `5` and `2` are the operands, and `+` is the operator. 

## Types of Operators

<tabs>
<tab title="Arithmetic Operators">

Arithmetic operators are used to perform arithmetic operations on values and variables. The following table lists the arithmetic operators in pseudocode:

| Operator | Description | Example |
| :--- | :--- | :--- |
| `+` | Addition | `5 + 2` evaluates to `7` |
| `-` | Subtraction | `5 - 2` evaluates to `3` |
| `*` | Multiplication | `5 * 2` evaluates to `10` |
| `/` | Division | `5 / 2` evaluates to `2.5` |
| `%` | Modulus | `5 % 2` evaluates to `1` |
| `^` | Exponentiation | `5 ^ 2` evaluates to `25` |

</tab>
<tab title="Assignment Operators">

Assignment operators are used to assign values to variables. The following table lists the assignment operators in pseudocode:

| Operator | Description | Example |
| :--- | :--- | :--- |
| `=` | Assign | `x = 5` assigns the value `5` to the variable `x` |
| `+=` | Add and assign | `x += 5` is equivalent to `x = x + 5` |
| `-=` | Subtract and assign | `x -= 5` is equivalent to `x = x - 5` |
| `*=` | Multiply and assign | `x *= 5` is equivalent to `x = x * 5` |
| `/=` | Divide and assign | `x /= 5` is equivalent to `x = x / 5` |
| `%=` | Modulus and assign | `x %= 5` is equivalent to `x = x % 5` |
| `^=` | Exponentiate and assign | `x ^= 5` is equivalent to `x = x ^ 5` |

</tab>
<tab title="Comparison Operators">

Comparison operators are used to compare two values. The following table lists the comparison operators in pseudocode:

| Operator | Description | Example |
| :--- | :--- | :--- |
| `==` | Equal to | `5 == 2` evaluates to `false` |
| `!=` | Not equal to | `5 != 2` evaluates to `true` |
| `<` | Less than | `5 < 2` evaluates to `false` |
| `>` | Greater than | `5 > 2` evaluates to `true` |
| `<=` | Less than or equal to | `5 <= 2` evaluates to `false` |
| `>=` | Greater than or equal to | `5 >= 2` evaluates to `true` |

</tab>
<tab title="Logical Operators">

Logical operators are used to combine multiple conditions. The following table lists the logical operators in pseudocode:

| Operator | Description | Example |
| :--- | :--- | :--- |
| `&&` | Logical AND | `5 > 2 && 5 < 10` evaluates to `true` |
| `||` | Logical OR | `5 > 2 || 5 < 10` evaluates to `true` |
| `!` | Logical NOT | `!(5 > 2)` evaluates to `false` |

</tab>
<tab title="Bitwise Operators">

Bitwise operators are used to perform bitwise operations on values. The following table lists the bitwise operators in pseudocode:

| Operator | Description | Example |
| :--- | :--- | :--- |
| `&` | Bitwise AND | `5 & 2` evaluates to `0` |
| `|` | Bitwise OR | `5 | 2` evaluates to `7` |
| `^` | Bitwise XOR | `5 ^ 2` evaluates to `7` |
| `~` | Bitwise NOT | `~5` evaluates to `-6` |
| `<<` | Left shift | `5 << 2` evaluates to `20` |
| `>>` | Right shift | `5 >> 2` evaluates to `1` |

</tab>
<tab title="Other Operators">

Other operators are used for various purposes. The following table lists the other operators in pseudocode:

| Operator | Description | Example |
| :--- | :--- | :--- |
| `()` | Parentheses | `(5 + 2) * 3` evaluates to `21` |
| `[]` | Brackets | `arr[0]` accesses the first element of the array `arr` |
| `.` | Dot | `obj.prop` accesses the property `prop` of the object `obj` |
| `?:` | Ternary | `5 > 2 ? 5 : 2` evaluates to `5` |
| `++` | Increment | `x++` is equivalent to `x = x + 1` |
| `--` | Decrement | `x--` is equivalent to `x = x - 1` |

</tab>

</tabs>



## Syntax

### Pseudocode {switcher-key="Pseudocode"}

<video src="https://youtu.be/p98cayTo1Go?feature=shared" width="900" mini-player="true"/>

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

### C++ {switcher-key="C++"}

<video src="https://youtu.be/7zlRqvbuCGU?feature=shared" width="900" mini-player="true"/>

#### Sample C++

```c++
#include <iostream>
using namespace std;

int main() {
    double length, width;
    cout << "Enter length: ";
    cin >> length;
    cout << "Enter width: ";
    cin >> width;

    double area = length * width;
    cout << "Area of the rectangle: " << area << endl;

    return 0;
}
```

#### Output C++

```text
Enter length: 5
Enter width: 2
Area of the rectangle: 10
```

### Python {switcher-key="Python"}

<video src="https://youtu.be/v5MR5JnKcZI?feature=shared" width="900" mini-player="true"/>

#### Sample Python

```python
length = float(input("Enter length: "))
width = float(input("Enter width: "))
area = length * width
print("Area of the rectangle:", area)
```

#### Output Python

```text
Enter length: 5
Enter width: 2
Area of the rectangle: 10.0
```

### Java {switcher-key="Java"}

<video src="https://youtu.be/QSsjB1tMPhA?feature=shared" width="900" mini-player="true"/>

#### Sample Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double length, width;
        System.out.print("Enter length: ");
        length = input.nextDouble();
        System.out.print("Enter width: ");
        width = input.nextDouble();

        double area = length * width;
        System.out.println("Area of the rectangle: " + area);
    }
}
```

#### Output Java

```text
Enter length: 5
Enter width: 2
Area of the rectangle: 10.0
```

### Go {switcher-key="Go"}

<video src="https://youtu.be/VSCZmSqaVDQ" width="900" mini-player="true"/>

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

```text
Enter length: 5
Enter width: 2
Area of the rectangle: 10
```
