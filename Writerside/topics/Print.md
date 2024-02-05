# Print (Formatted) Statements

#### What is a formatted print statement?

<note>
<b>Definition &amp; Use</b>

A formatted print statement is a statement that prints a value to the console. A formatted print statement is used to print a value to the console. A formatted print statement is used to print a value to the console in a specific format.
</note>

The following example shows a formatted print statement:

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

int main() {
    int i = 10;
    float f = 10.10;
    char c[] = "ten";
    printf("Printing int: %d\n", i);
    printf("Printing float: %f\n", f);
    printf("Printing character: %s\n", c);
    printf("Printing all: %d %f %s\n", i, f, c);
    return 0;
}
```

<br/>

```c++
// Output

Printing int: 10
Printing float: 10.1
Printing character: ten
Printing all: 10 10.1 ten
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">

```python
def main():
    i = 10
    f = 10.10101010
    c = "ten"
    
    # Using f-strings (formatted strings)
    f"Printing int: {i}")
    f"Printing float: {f}")
    f"Printing character: {c}")
    f"Printing all: {i} {f} {c}")
    
    # Using the format() method
    f('{0} {1} {2}'.format("Printing int:", i, "\n"))
    f('{0} {1} {2}'.format("Printing float:", f, "\n"))
    f('{0} {1} {2}'.format("Printing character:", c, "\n"))
    f('{0} {1} {2} {3} {4}'.format("Printing all:", i, f, c, "\n"))
    
    # Formatting using the % operator
    f("Printing int: %d" % i)
    f("Printing float: %f" % f)
    f("Printing character: %s" % c)
    f("Printing all: %d %f %s" % (i, f, c))
    
    # Formatting with defined width and precision
    f("Printing float: %10.2f" % f)
    f("Printing all: %10d %10.2f %10s" % (i, f, c))
    
    # Using the print() function
    print("Printing int:", i)
    print("Printing float:", f)
    print("Printing character:", c)
    print("Printing all:", i, f, c)
    
if __name__ == "__main__":
    main()
```

<br/>

```python
# Output

Printing int: 10
Printing float: 10.1010101
Printing character: ten
Printing all: 10 10.1010101 ten

Printing int: 10
Printing float: 10.1010101
Printing character: ten
Printing all: 10 10.1010101 ten

Printing int: 10
Printing float: 10.101010
Printing character: ten
Printing all: 10 10.101010 ten

Printing int: 10
Printing float: 10.101010
Printing character: ten
Printing all: 10 10.101010 ten

Printing float:      10.10
Printing all:         10      10.10        ten

Printing int: 10
Printing float: 10.1010101
Printing character: ten
Printing all: 10 10.1010101 ten
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">

```java
public class Main {

    public static void main(String[] args) {
        int i = 10;
        double f = 10.10;
        String c = "ten";
        System.out.printf("Printing int: %d\n", i);
        System.out.printf("Printing float: %f\n", f);
        System.out.printf("Printing character: %s\n", c);
        System.out.printf("Printing all: %d %f %s\n", i, f, c);
    }
}
```

<br/>

```java
// Output

Printing int: 10
Printing float: 10.1
Printing character: ten
Printing all: 10 10.1 ten
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">

```go
package main
import "fmt"

func main() {
    i := 10
    f := 10.10
    c := "ten"
    fmt.Printf("Printing int: %d\n", i)
    fmt.Printf("Printing float: %f\n", f)
    fmt.Printf("Printing character: %s\n", c)
    fmt.Printf("Printing all: %d %f %s\n", i, f, c)
}
```

<br/>

```go
// Output

Printing int: 10
Printing float: 10.1
Printing character: ten
Printing all: 10 10.1 ten
```
{ collapsible="true" }

</procedure>