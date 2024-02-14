# Exception Handling


<procedure>

![img](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2018/11/Exception-flow-Java-Exception-Handling-Edureka.png)
{width="900" thumbnail="true"}
</procedure>

<note>
<p>Definition</p>
<p>Exception handling is a mechanism to handle runtime errors, such as division by zero, file not found, or network failure, in a program. It allows the program to gracefully recover from errors and continue execution without crashing.</p>

<p>File I/O operations can raise exceptions, such as file not found, permission denied, or disk full. It is important to handle these exceptions to ensure the program behaves as expected.</p>

<p>Common exception handling techniques include try-catch blocks, throwing custom exceptions, and using built-in exception classes.</p>
</note>

### Try-Catch Blocks

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="try_catch.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    try {
        // Create a file object
        ofstream file;

        // Open the file
        file.open("example.txt");

        // Write to the file
        file << "Hello World!";

        // Close the file
        file.close();
    } catch (const exception& e) {
        cout << "Error: " << e.what() << endl;
    }

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="try_catch.jpeg" mini-player="true" width="900" />

<br/>

```python
try:
    # Open the file
    file = open("example.txt", "w")

    # Write to the file
    file.write("Hello World!")

    # Close the file
    file.close()
except Exception as e:
    print("Error:", e)
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="try_catch.jpeg" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Create a file object
            PrintWriter outputFile = new PrintWriter("example.txt");

            // Write to the file
            outputFile.println("Hello World!");

            // Close the file
            outputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="try_catch.jpeg" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "fmt"
    "io/ioutil"
)

func main() {
    // Read the file
    data, err := ioutil.ReadFile("example.txt")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Throwing Custom Exceptions

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="custom_ex.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    try {
        // Create a file object
        ofstream file;

        // Open the file
        file.open("example.txt");

        // Write to the file
        file << "Hello World!";

        // Close the file
        file.close();
    } catch (const exception& e) {
        cout << "Error: " << e.what() << endl;
    }

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="custom_ex.jpeg" mini-player="true" width="900" />

<br/>

```python
try:
    # Open the file
    file = open("example.txt", "w")

    # Write to the file
    file.write("Hello World!")

    # Close the file
    file.close()
except Exception as e:
    print("Error:", e)
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="custom_ex.jpeg" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Create a file object
            PrintWriter outputFile = new PrintWriter("example.txt");

            // Write to the file
            outputFile.println("Hello World!");

            // Close the file
            outputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="custom_ex.jpeg" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "fmt"
    "io/ioutil"
)

func main() {
    // Read the file
    data, err := ioutil.ReadFile("example.txt")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Using Built-In Exception Classes

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="built_in_ex.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    try {
        // Create a file object
        ofstream file;

        // Open the file
        file.open("example.txt");

        // Write to the file
        file << "Hello World!";

        // Close the file
        file.close();
    } catch (const exception& e) {
        cout << "Error: " << e.what() << endl;
    }

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="built_in_ex.jpeg" mini-player="true" width="900" />

<br/>

```python
try:
    # Open the file
    file = open("example.txt", "w")

    # Write to the file
    file.write("Hello World!")

    # Close the file
    file.close()
except Exception as e:
    print("Error:", e)
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="built_in_ex.jpeg" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Create a file object
            PrintWriter outputFile = new PrintWriter("example.txt");

            // Write to the file
            outputFile.println("Hello World!");

            // Close the file
            outputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" preview-src="built_in_ex.jpeg" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "fmt"
    "io/ioutil"
)

func main() {
    // Read the file
    data, err := ioutil.ReadFile("example.txt")
    if err != nil {
        fmt.Println("Error:", err)
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>