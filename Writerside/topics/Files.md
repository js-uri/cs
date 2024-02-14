---
switcher-label: Language
---

# File Handling

![image](https://static.javatpoint.com/core/images/types-of-exception-handling.png)
{ centered=true }

## Overview

<note>
<p>Definition</p>
<p>File Input/Output (I/O) refers to the process of reading data from files or writing data to files in a computer program. This functionality allows programs to store and retrieve information persistently, making it useful for various tasks like saving configurations, storing user data, or processing large datasets.</p>
</note>

<table style="none">
<tr>
<td>Reading configuration files to set program parameters.</td><td>Saving and loading game progress or user data in games or applications.</td><td>Processing large datasets, such as reading from CSV files.</td>
</tr>
<tr>
<td>Logging information, debugging, and error handling.</td><td></td><td>Creating and managing databases.</td>
</tr>
</table>

<table>
<tr>
<th>Pros</th><th>Cons</th>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Data Persistence">Files allow data to be stored beyond the program’s runtime, making it available for future use.</def>
<def title="Data Sharing">Files enable data exchange between different programs and systems.</def>
<def title="Scalability">File I/O can handle large volumes of data efficiently.</def>
<def title="Portability">Files can be easily transformed between different platforms</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Slower Access">Reading from and writing to files is generally slower compared to in-memory operations.</def>
<def title="Error Handling">File operations can lead to potential errors, such as file not found or permissions issues.</def>
<def title="Security Risks">Improper handling of files can lead to security vulnerabilities.</def>
</deflist>
</td>
</tr>
</table>

## Syntax

### Opening, Reading, and Closing a File

<procedure switcher-key="C++">

<video src="https://youtu.be/N1wSFA6VNuM?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file
    file.open("example.txt");

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/DmHSwTiD5Tk?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file
file = open("example.txt", "w")

# Write to the file
file.write("Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/hgF21imQ_Is?feature=shared" mini-player="true" width="900" />

<br/>

```java
// Java uses Scanner to read data from the file. The hasNextInt() method checks 
// if the file has more integers, and nextInt() reads the next integer.

import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            File file = new File("data.txt");
            Scanner inputFile = new Scanner(file);
            while (inputFile.hasNextInt()) {
                int num = inputFile.nextInt();
                System.out.print(num + " ");
            }
            inputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/N1wSFA6VNuM?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>


## File Modes

<note>
<p>Definition</p>

<p>File modes specify the type of operations that can be performed on a file. They define whether a file can be read from, written to, or both. Common file modes include read, write, append, and binary modes.</p>

<p>File modes are specified as part of the file opening process and determine the behavior of the file object.</p>

<p>It is important to choose the correct file mode to ensure the file is accessed and modified as intended.</p>

</note>

### Read Mode

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ifstream file;

    // Open the file in read mode
    file.open("example.txt", ios::in);

    // Read from the file
    string data;
    file >> data;

    // Close the file
    file.close();

    return 0;
}
```
    
</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in read mode
file = open("example.txt", "r")

# Read from the file
data = file.read()

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Open the file in read mode
            File file = new File("example.txt");
            Scanner inputFile = new Scanner(file);

            // Read from the file
            while (inputFile.hasNextLine()) {
                String data = inputFile.nextLine();
                System.out.println(data);
            }

            // Close the file
            inputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Write Mode

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file in write mode
    file.open("example.txt", ios::out);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in write mode
file = open("example.txt", "w")

# Write to the file
file.write("Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Append Mode

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file in append mode
    file.open("example.txt", ios::app);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in append mode
file = open("example.txt", "a")

# Write to the file
file.write("Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Create a file object
            PrintWriter outputFile = new PrintWriter(new FileWriter("example.txt", true));

            // Write to the file
            outputFile.println("Hello World!");

            // Close the file
            outputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Binary Mode

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;
    
int main() {
    // Create a file object
    ofstream file;

    // Open the file in binary mode
    file.open("example.txt", ios::binary);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in binary mode
file = open("example.txt", "wb")

# Write to the file
file.write(b"Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

## File Operations

<note>
<p>Definition</p>

<p>File operations refer to the various tasks that can be performed on files, such as reading, writing, appending, and deleting. These operations allow programs to interact with files and manipulate their contents.</p>

<p>Common file operations include reading data from files, writing data to files, appending data to files, and deleting files.</p>

<p>It is important to handle file operations carefully to ensure data integrity and security.</p>

</note>

### Reading Data from Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ifstream file;

    // Open the file in read mode
    file.open("example.txt", ios::in);

    // Read from the file
    string data;
    file >> data;

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in read mode
file = open("example.txt", "r")

# Read from the file
data = file.read()

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Open the file in read mode
            File file = new File("example.txt");
            Scanner inputFile = new Scanner(file);

            // Read from the file
            while (inputFile.hasNextLine()) {
                String data = inputFile.nextLine();
                System.out.println(data);
            }

            // Close the file
            inputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Writing Data to Files

<procedure switcher-key="C++">
    
<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file in write mode
    file.open("example.txt", ios::out);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in write mode
file = open("example.txt", "w")

# Write to the file
file.write("Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Appending Data to Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file in append mode
    file.open("example.txt", ios::app);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in append mode
file = open("example.txt", "a")

# Write to the file
file.write("Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class FileIOJava {
    public static void main(String[] args) {
        try {
            // Create a file object
            PrintWriter outputFile = new PrintWriter(new FileWriter("example.txt", true));

            // Write to the file
            outputFile.println("Hello World!");

            // Close the file
            outputFile.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Deleting Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Delete the file
    remove("example.txt");

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
import os

# Delete the file
os.remove("example.txt")
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.File;

public class FileIOJava {
    public static void main(String[] args) {
        // Delete the file
        File file = new File("example.txt");
        file.delete();
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```go
package main

import "os"

func main() {
    // Delete the file
    err := os.Remove("example.txt")
    if err != nil {
        panic(err)
    }
}
```

</procedure>

## File Formats

<note>

<p>Definition</p>

<p>File formats refer to the structure and organization of data within a file. They define how data is stored, encoded, and interpreted by programs. Common file formats include text files, binary files, and structured files like JSON and XML.</p>

<p>Choosing the right file format is important for data integrity, interoperability, and performance. It is essential to understand the characteristics and use cases of different file formats to make informed decisions.</p>

</note>

### Text Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>

using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file in write mode
    file.open("example.txt", ios::out);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in write mode
file = open("example.txt", "w")

# Write to the file
file.write("Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### Binary Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // Create a file object
    ofstream file;

    // Open the file in binary mode
    file.open("example.txt", ios::binary);

    // Write to the file
    file << "Hello World!";

    // Close the file
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
# Open the file in binary mode
file = open("example.txt", "wb")

# Write to the file
file.write(b"Hello World!")

# Close the file
file.close()
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
            System.out.println("Error opening file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

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
        fmt.Println("Error opening file.")
        return
    }

    // Print the file contents
    fmt.Println(string(data))
}
```

</procedure>

### JSON Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
#include <nlohmann/json.hpp>
using namespace std;

int main() {
    // Create a JSON object
    nlohmann::json data = {
        {"name", "John"},
        {"age", 30},
        {"city", "New York"}
    };

    // Write the JSON object to a file
    ofstream file("example.json");
    file << data;
    file.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
import json

# Create a JSON object
data = {
    "name": "John",
    "age": 30,
    "city": "New York"
}

# Write the JSON object to a file
with open("example.json", "w") as file:
    json.dump(data, file)
```

</procedure>


<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.FileWriter;
import java.io.IOException;
import org.json.simple.JSONObject;

public class FileIOJava {
    public static void main(String[] args) {
        // Create a JSON object
        JSONObject data = new JSONObject();
        data.put("name", "John");
        data.put("age", 30);
        data.put("city", "New York");

        // Write the JSON object to a file
        try (FileWriter file = new FileWriter("example.json")) {
            file.write(data.toJSONString());
        } catch (IOException e) {
            System.out.println("Error writing to file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "encoding/json"
    "fmt"
    "os"
)

func main() {
    // Create a JSON object
    data := map[string]interface{}{
        "name": "John",
        "age": 30,
        "city": "New York",
    }

    // Write the JSON object to a file
    file, err := os.Create("example.json")
    if err != nil {
        fmt.Println("Error creating file.")
        return
    }
    defer file.Close()

    encoder := json.NewEncoder(file)
    err = encoder.Encode(data)
    if err != nil {
        fmt.Println("Error writing to file.")
    }
}
```

</procedure>

### XML Files

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
#include <pugixml.hpp>
using namespace std;

int main() {
    // Create an XML document
    pugi::xml_document doc;
    pugi::xml_node data = doc.append_child("data");
    data.append_child("name").text() = "John";
    data.append_child("age").text() = "30";
    data.append_child("city").text() = "New York";

    // Write the XML document to a file
    doc.save_file("example.xml");

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
import xml.etree.ElementTree as ET

# Create an XML document
data = ET.Element("data")
name = ET.SubElement(data, "name")
name.text = "John"
age = ET.SubElement(data, "age")
age.text = "30"
city = ET.SubElement(data, "city")
city.text = "New York"

# Write the XML document to a file
tree = ET.ElementTree(data)
tree.write("example.xml")
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.FileWriter;
import java.io.IOException;
import org.json.simple.JSONObject;

public class FileIOJava {
    public static void main(String[] args) {
        // Create an XML document
        JSONObject data = new JSONObject();
        data.put("name", "John");
        data.put("age", 30);
        data.put("city", "New York");

        // Write the XML document to a file
        try (FileWriter file = new FileWriter("example.xml")) {
            file.write(data.toJSONString());
        } catch (IOException e) {
            System.out.println("Error writing to file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "encoding/json"
    "fmt"
    "os"
)

func main() {
    // Create an XML document
    data := map[string]interface{}{
        "name": "John",
        "age": 30,
        "city": "New York",
    }

    // Write the XML document to a file
    file, err := os.Create("example.xml")
    if err != nil {
        fmt.Println("Error creating file.")
        return
    }
    defer file.Close()

    encoder := json.NewEncoder(file)
    err = encoder.Encode(data)
    if err != nil {
        fmt.Println("Error writing to file.")
    }
}
```

</procedure>

## File Compression

<note>

<p>Definition</p>

<p>File compression refers to the process of reducing the size of a file by encoding its contents using a compression algorithm. Compressed files take up less storage space and can be transferred more quickly over networks. Common file compression formats include ZIP, GZIP, and BZIP2.</p>

<p>File compression is useful for reducing storage and bandwidth requirements, especially for large files. It is important to choose the right compression format and algorithm based on the specific use case and requirements.</p>

</note>

### ZIP Compression


<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
#include <zip.h>
using namespace std;

int main() {
    // Create a ZIP archive
    zip_t *zip = zip_open("example.zip", ZIP_CREATE | ZIP_TRUNCATE, NULL);

    // Add a file to the ZIP archive
    zip_file_t *file = zip_fopen(zip, "example.txt", ZIP_FL_OVERWRITE);
    zip_fwrite(file, "Hello World!", 12);
    zip_fclose(file);

    // Close the ZIP archive
    zip_close(zip);

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
import zipfile

# Create a ZIP archive
with zipfile.ZipFile("example.zip", "w") as zip:
    # Add a file to the ZIP archive
    zip.write("example.txt")
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.ZipEntry;
import java.util.zip.ZipOutputStream;

public class FileIOJava {
    public static void main(String[] args) {
        // Create a ZIP archive
        try (FileOutputStream file = new FileOutputStream("example.zip");
             ZipOutputStream zip = new ZipOutputStream(file)) {
            // Add a file to the ZIP archive
            File source = new File("example.txt");
            zip.putNextEntry(new ZipEntry(source.getName()));
            byte[] buffer = new byte[1024];
            int length;
            try (FileInputStream in = new FileInputStream(source)) {
                while ((length = in.read(buffer)) > 0) {
                    zip.write(buffer, 0, length);
                }
            }
            zip.closeEntry();
        } catch (IOException e) {
            System.out.println("Error creating ZIP archive.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```go

package main

import (
    "archive/zip"
    "os"
)

func main() {
    // Create a ZIP archive
    file, err := os.Create("example.zip")
    if err != nil {
        panic(err)
    }
    defer file.Close()

    zipWriter := zip.NewWriter(file)
    defer zipWriter.Close()

    // Add a file to the ZIP archive
    fileToZip, err := os.Open("example.txt")
    if err != nil {
        panic(err)
    }
    defer fileToZip.Close()

    info, err := fileToZip.Stat()
    if err != nil {
        panic(err)
    }

    header, err := zip.FileInfoHeader(info)
    if err != nil {
        panic(err)
    }
    header.Method = zip.Deflate

    writer, err := zipWriter.CreateHeader(header)
    if err != nil {
        panic(err)
    }

    _, err = io.Copy(writer, fileToZip)
    if err != nil {
        panic(err)
    }
}
```

</procedure>

### GZIP Compression

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++  
#include <fstream>
#include <iostream>
#include <zlib.h>
using namespace std;

int main() {
    // Open the input file
    ifstream inputFile("example.txt", ios::binary);
    if (!inputFile) {
        cerr << "Error opening file." << endl;
        return 1;
    }

    // Open the output file
    ofstream outputFile("example.txt.gz", ios::binary);
    if (!outputFile) {
        cerr << "Error creating file." << endl;
        return 1;
    }

    // Compress the input file
    z_stream stream;
    stream.zalloc = Z_NULL;
    stream.zfree = Z_NULL;
    stream.opaque = Z_NULL;
    stream.avail_in = 0;
    stream.next_in = Z_NULL;
    int ret = deflateInit(&stream, Z_BEST_COMPRESSION);
    if (ret != Z_OK) {
        cerr << "Error initializing compression." << endl;
        return 1;
    }

    char in[1024];
    char out[1024];
    do {
        inputFile.read(in, sizeof(in));
        stream.avail_in = inputFile.gcount();
        stream.next_in = (Bytef *)in;
        do {
            stream.avail_out = sizeof(out);
            stream.next_out = (Bytef *)out;
            ret = deflate(&stream, Z_FINISH);
            outputFile.write(out, sizeof(out) - stream.avail_out);
        } while (stream.avail_out == 0);
    } while (inputFile);

    (void)deflateEnd(&stream);

    // Close the files
    inputFile.close();
    outputFile.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
import gzip

# Open the input file
with open("example.txt", "rb") as inputFile:
    # Open the output file
    with gzip.open("example.txt.gz", "wb") as outputFile:
        # Compress the input file
        outputFile.writelines(inputFile)
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.GZIPOutputStream;

public class FileIOJava {
    public static void main(String[] args) {
        // Open the input file
        try (FileInputStream inputFile = new FileInputStream("example.txt")) {
            // Open the output file
            try (GZIPOutputStream outputFile = new GZIPOutputStream(new FileOutputStream("example.txt.gz"))) {
                // Compress the input file
                byte[] buffer = new byte[1024];
                int length;
                while ((length = inputFile.read(buffer)) > 0) {
                    outputFile.write(buffer, 0, length);
                }
            }
        } catch (IOException e) {
            System.out.println("Error compressing file.");
        }
    }
}
```

</procedure>

<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "compress/gzip"
    "io"
    "os"
)

func main() {
    // Open the input file
    inputFile, err := os.Open("example.txt")
    if err != nil {
        panic(err)
    }
    defer inputFile.Close()

    // Open the output file
    outputFile, err := os.Create("example.txt.gz")
    if err != nil {
        panic(err)
    }
    defer outputFile.Close()

    // Compress the input file
    writer := gzip.NewWriter(outputFile)
    defer writer.Close()

    _, err = io.Copy(writer, inputFile)
    if err != nil {
        panic(err)
    }
}
```

</procedure>

### BZIP2 Compression

<procedure switcher-key="C++">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```c++
#include <fstream>
#include <iostream>
#include <bzlib.h>
using namespace std;

int main() {
    // Open the input file
    ifstream inputFile("example.txt", ios::binary);
    if (!inputFile) {
        cerr << "Error opening file." << endl;
        return 1;
    }

    // Open the output file
    ofstream outputFile("example.txt.bz2", ios::binary);
    if (!outputFile) {
        cerr << "Error creating file." << endl;
        return 1;
    }

    // Compress the input file
    BZFILE *bzfile = BZ2_bzWriteOpen(&bzerror, outputFile, 9, 0, 0);
    if (bzerror != BZ_OK) {
        cerr << "Error initializing compression." << endl;
        return 1;
    }

    char in[1024];
    int bytesRead;
    do {
        inputFile.read(in, sizeof(in));
        bytesRead = inputFile.gcount();
        BZ2_bzWrite(&bzerror, bzfile, in, bytesRead);
    } while (inputFile);

    BZ2_bzWriteClose(&bzerror, bzfile, 0, NULL, NULL);
    if (bzerror != BZ_OK) {
        cerr << "Error finalizing compression." << endl;
        return 1;
    }

    // Close the files
    inputFile.close();
    outputFile.close();

    return 0;
}
```

</procedure>

<procedure switcher-key="Python">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```python
import bz2

# Open the input file
with open("example.txt", "rb") as inputFile:
    # Open the output file
    with bz2.open("example.txt.bz2", "wb") as outputFile:
        # Compress the input file
        outputFile.writelines(inputFile)
```

</procedure>

<procedure switcher-key="Java">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import org.apache.commons.compress.compressors.bzip2.BZip2CompressorOutputStream;

public class FileIOJava {
    public static void main(String[] args) {
        // Open the input file
        try (FileInputStream inputFile = new FileInputStream("example.txt")) {
            // Open the output file
            try (BZip2CompressorOutputStream outputFile = new BZip2CompressorOutputStream(new FileOutputStream("example.txt.bz2"))) {
                // Compress the input file
                byte[] buffer = new byte[1024];
                int length;
                while ((length = inputFile.read(buffer)) > 0) {
                    outputFile.write(buffer, 0, length);
                }
            }
        } catch (IOException e) {
            System.out.println("Error compressing file.");
        }
    }
}
```

</procedure>


<procedure switcher-key="Go">

<video src="https://youtu.be/3zv8v3X3v4E?feature=shared" mini-player="true" width="900" />

<br/>

```go
package main

import (
    "compress/bzip2"
    "io"
    "os"
)

func main() {
    // Open the input file
    inputFile, err := os.Open("example.txt")
    if err != nil {
        panic(err)
    }
    defer inputFile.Close()

    // Open the output file
    outputFile, err := os.Create("example.txt.bz2")
    if err != nil {
        panic(err)
    }
    defer outputFile.Close()

    // Compress the input file
    writer := bzip2.NewWriter(outputFile)
    defer writer.Close()

    _, err = io.Copy(writer, inputFile)
    if err != nil {
        panic(err)
    }
}
```

</procedure>
