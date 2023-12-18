---
switcher-label: Language
---

# Jumps

<procedure switcher-key="C++">
<video src="https://youtu.be/a3IZ8WaIFAA?feature=shared" preview-src="jumps1.jpeg" mini-player="true" width="900" /> 
</procedure>
<procedure switcher-key="Python">
<video src="https://youtu.be/97NdNoA3XUQ?feature=shared" preview-src="jumps1.jpeg" mini-player="true" width="900" /> 
</procedure>
<procedure switcher-key="Java">
<video src="https://youtu.be/aITdnsUTeek?feature=shared" preview-src="jumps1.jpeg" mini-player="true" width="900" /> 
</procedure>
<procedure switcher-key="Go">
<video src="https://youtu.be/ZWBA3l818y0?feature=shared" preview-src="jumps1.jpeg" mini-player="true" width="900" />
</procedure>



## Overview

<note>
<b>Definition &amp; Use</b>

A jump is a statement that transfers control to another part of the program.
</note>

## Types of Jumps

There are three types of jumps:

<procedure>
<deflist collapsible="true">
<def title="Unconditional">
An unconditional jump transfers control to another part of the program without any conditions.
</def>
<def title="Conditional">
A conditional jump transfers control to another part of the program if a condition is met.
</def>
<def title="Nested">
A nested jump is a jump within a jump.
</def>
</deflist>
</procedure>

## Syntax

### Goto Statement

<procedure switcher-key="C++">
<b>C++</b>

```text
goto label
```

```c++
#include <iostream>

using namespace std;

int main()
{
    goto label;

    cout << "Hello World!" << endl;

    label:
    cout << "Hello World!" << endl;

    return 0;
}
```

Output

```text
Hello World!
```

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```text
goto label
```

```python
print("Hello World!")

label:
print("Hello World!")
```

Output

```text
Hello World!
```

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```text
goto label
```

```java
public class Main {
    public static void main(String[] args) {
        goto label;

        System.out.println("Hello World!");

        label:
        System.out.println("Hello World!");
    }
}
```

Output

```text
Hello World!
```

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```text
goto label
```

```go
package main

import "fmt"

func main() {
    goto label

    fmt.Println("Hello World!")

    label:
    fmt.Println("Hello World!")
}
```

Output

```text
Hello World!
```

</procedure>



### Break Statement

<procedure switcher-key="C++">
<b>C++</b>

```text
break
```

```c++
#include <iostream>

using namespace std;

int main()
{
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            break;
        }
        cout << i << endl;
    }
    return 0;
}
```

Output

```text
0
1
2
3
4
```
</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```text
break
```

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

Output

```text
0
1
2
3
4
```
</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```text
break
```

```java
public class Main {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i == 5) {
                break;
            }
            System.out.println(i);
        }
    }
}
```

Output

```text
0
1
2
3
4
```

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```text
break
```

```go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i == 5 {
            break
        }
        fmt.Println(i)
    }
}
```

Output

```text
0
1
2
3
4
```

</procedure>



### Continue Statement

<procedure switcher-key="C++">
<b>C++</b>

```text
continue
```

```c++
#include <iostream>

using namespace std;

int main()
{
    for (int i = 0; i < 10; i++) {
        if (i == 5) {
            continue;
        }
        cout << i << endl;
    }
    return 0;
}
```

Output

```text
0
1
2
3
4
6
7
8
9
```
</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```text
continue
```

```python
for i in range(10):
    if i == 5:
        continue
    print(i)
```

Output

```text
0
1
2
3
4
6
7
8
9
```

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```text
continue
```

```java

public class Main {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i == 5) {
                continue;
            }
            System.out.println(i);
        }
    }
}
```

Output

```text

0
1
2
3
4
6
7
8
9
```

</procedure>

<procedure switcher-key="Go">

<b>Go</b>

```text
continue
```

```go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i == 5 {
            continue
        }
        fmt.Println(i)
    }
}
```

Output

```text
0
1
2
3
4
6
7
8
9
```

</procedure>


### Return Statement

<procedure switcher-key="C++">
<b>C++</b>

```text
return
```

```c++  

#include <iostream>

using namespace std;

int main()
{
    return 0;
}
```

Output

```text 
0
```
</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```text
return
```

```python
def main():
    return 0
```

Output

```text
0
```
</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```text
return
```

```java
public class Main {
    public static void main(String[] args) {
        return 0;
    }
}
```

Output

```text
0
```
</procedure>

<procedure switcher-key="Go">

<b>Go</b>

```text
return
```

```go
package main
    
import "fmt"

func main() {
    return 0
}
```

Output

```text
0
```

</procedure>


### Exit Statement

<procedure switcher-key="C++">
<b>C++</b>

```text
exit
```

```c++
#include <iostream>

using namespace std;

int main()
{
    exit(0);
}
```

Output

```text
0
```
</procedure>

<procedure switcher-key="Python">

<b>Python</b>

```text
exit
```

```python
import sys

def main():
    sys.exit(0)
```

Output

```text
0
```

</procedure>

<procedure switcher-key="Java">

<b>Java</b>

```text
exit
```

```java
public class Main {
    public static void main(String[] args) {
        System.exit(0);
    }
}
```

Output

```text
0
```

</procedure>

<procedure switcher-key="Go">

<b>Go</b>

```text
exit
```

```go
package main

import "os"

func main() {
    os.Exit(0)
}
```

Output

```text
0
```

</procedure>

### Throw Statement

<procedure switcher-key="C++">
<b>C++</b>

```text
throw
```

```c++
#include <iostream>

using namespace std;

int main()
{
    throw 0;
}
```

Output

```text
0
```
</procedure>

<procedure switcher-key="Python">

<b>Python</b>

```text
throw
```

```python
def main():
    raise Exception(0)
```

Output

```text
0
```

</procedure>

<procedure switcher-key="Java">

<b>Java</b>

```text
throw
```

```java
public class Main {
    public static void main(String[] args) {
        throw 0;
    }
}
```

Output

```text
0
```

</procedure>

<procedure switcher-key="Go">

<b>Go</b>

```text
throw
```

```go
package main

func main() {
    panic(0)
}
```

Output

```text
0
```

</procedure>