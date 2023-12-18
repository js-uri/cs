---
switcher-label: Language
---

# Iterations

<video src="https://youtu.be/jNl5gJ_xSNQ?feature=shared" preview-src="iterables1.jpeg" mini-player="true" width="900" switcher-key="C++" /> 
<video src="https://youtu.be/94UHCEmprCY?feature=shared"  preview-src="iterables1.jpeg" mini-player="true" width="900" switcher-key="Python" /> 
<video src="https://youtu.be/RWuHw02ZcVs?feature=shared"  preview-src="iterables1.jpeg" mini-player="true" width="900" switcher-key="Java" /> 
<video src="https://youtu.be/CL13xV2dHCg?feature=shared"  preview-src="iterables1.jpeg" mini-player="true" width="900" switcher-key="Go" />

## Overview

<note>
<b>Definition & Use</b>

An iteration is a single execution of a set of instructions. Iterations are used to repeat a set of instructions a specified number of times or until a condition is met.
</note>

## Entry Controlled vs. Exit Controlled

An iteration is either entry controlled or exit controlled. In an entry controlled iteration, the condition is evaluated before the first iteration. In an exit controlled iteration, the condition is evaluated after the first iteration. 

## Types of Iterations

There are three types of iterations:

<procedure>
<deflist collapsible="true">
<def title="Counted">
A counted iteration repeats a set of instructions a specified number of times. A counted iteration is also known as a definite iteration.
</def>
<def title="Conditional">
A conditional iteration repeats a set of instructions until a condition is met. A conditional iteration is also known as an indefinite iteration.
</def>
<def title="Nested">
A nested iteration is an iteration within an iteration.
</def>
</deflist>
</procedure>

## Syntax

### For Loop 

<procedure switcher-key="C++">
<compare first-title="Pseudocode" second-title="C++">

```text
for (initialization; condition; increment/decrement) {
    // instructions
}
```

```c++
#include <iostream>

using namespace std;

int main()
{
    for (int i = 0; i < 10; i++) {
        cout << i << endl;
    }
    return 0;
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Python">
<compare first-title="Pseudocode" second-title="Python">

```text
for (initialization; condition; increment/decrement) {
    // instructions
}
```

```python
for i in range(10):
    print(i)
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Java" >
<compare first-title="Pseudocode" second-title="Java">

```text
for (initialization; condition; increment/decrement) {
    // instructions
}
```

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            System.out.println(i);
        }
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Go">
<compare first-title="Pseudocode" second-title="Go">

```text
for (initialization; condition; increment/decrement) {
    // instructions
}
```

```go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        fmt.Println(i)
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>




### While Loop

<procedure switcher-key="C++" >
<compare first-title="Pseudocode" second-title="C++">

```text
while (condition) {
    // instructions
}
```

```c++
#include <iostream>

using namespace std;

int main()
{
    int i = 0;
    while (i < 10) {
        cout << i << endl;
        i++;
    }
    return 0;
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Python" >
<compare first-title="Pseudocode" second-title="Python">

```text
while (condition) {
    // instructions
}
```

```python
i = 0
while i < 10:
    print(i)
    i += 1
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Java" >
<compare first-title="Pseudocode" second-title="Java">

```text
while (condition) {
    // instructions
}
```

```java
public class Main {
    public static void main(String[] args) {
        int i = 0;
        while (i < 10) {
            System.out.println(i);
            i++;
        }
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Go" >
<compare first-title="Pseudocode" second-title="Go">

```text
while (condition) {
    // instructions
}
```

```go
package main

import "fmt"

func main() {
    i := 0
    for i < 10 {
        fmt.Println(i)
        i++
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>


### Do While Loop

<procedure switcher-key="C++" >
<compare first-title="Pseudocode" second-title="C++">

```text
do {
    // instructions
} while (condition);
```

```c++

#include <iostream>

using namespace std;

int main()
{
    int i = 0;
    do {
        cout << i << endl;
        i++;
    } while (i < 10);
    return 0;
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Python" >
<compare first-title="Pseudocode" second-title="Python">

```text
do {
    // instructions
} while (condition);
```

```python
i = 0
while True:
    print(i)
    i += 1
    if i >= 10:
        break
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Java" >
<compare first-title="Pseudocode" second-title="Java">

```text
do {
    // instructions
} while (condition);
```

```java
public class Main {
    public static void main(String[] args) {
        int i = 0;
        do {
            System.out.println(i);
            i++;
        } while (i < 10);
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Go" >
<compare first-title="Pseudocode" second-title="Go">

```text
do {
    // instructions
} while (condition);
```

```go
package main

import "fmt"

func main() {
    i := 0
    for {
        fmt.Println(i)
        i++
        if i >= 10 {
            break
        }
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
0
1
2
3
4
5
6
7
8
9
```
</def>
</deflist>
</procedure>



### For Each Loop

<procedure  switcher-key="C++">
<compare first-title="Pseudocode" second-title="C++">

```text
for (item in collection) {
    // instructions
}
```

```c++

#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector<int> v = {1, 2, 3, 4, 5};
    for (int i : v) {
        cout << i << endl;
    }
    return 0;
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text
1
2
3
4
5
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Python" >
<compare first-title="Pseudocode" second-title="Python">

```text
for (item in collection) {
    // instructions
}
```

```python
v = [1, 2, 3, 4, 5]
for i in v:
    print(i)
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
1
2
3
4
5
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Java" >
<compare first-title="Pseudocode" second-title="Java">

```text
for (item in collection) {
    // instructions
}
```

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> v = new ArrayList<Integer>();
        v.add(1);
        v.add(2);
        v.add(3);
        v.add(4);
        v.add(5);
        for (int i : v) {
            System.out.println(i);
        }
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
1
2
3
4
5
```
</def>
</deflist>
</procedure>

<procedure switcher-key="Go" >
<compare first-title="Pseudocode" second-title="Go">

```text
for (item in collection) {
    // instructions
}
```

```go
package main

import "fmt"

func main() {
    v := []int{1, 2, 3, 4, 5}
    for _, i := range v {
        fmt.Println(i)
    }
}
```

</compare>

<deflist collapsible="true" default-state="collapsed">
<def title="Output">

```text 
1
2
3
4
5
```
</def>
</deflist>
</procedure>































