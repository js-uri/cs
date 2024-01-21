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

<video src="https://youtu.be/N1wSFA6VNuM?feature=shared" preview-src="fileIO.png" mini-player="true" width="900" />

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

<video src="https://youtu.be/DmHSwTiD5Tk?feature=shared" preview-src="fileIO.png" mini-player="true" width="900" />

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

<video src="https://youtu.be/hgF21imQ_Is?feature=shared" preview-src="fileIO.png" mini-player="true" width="900" />

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

<video src="https://youtu.be/N1wSFA6VNuM?feature=shared" preview-src="fileIO.png" mini-player="true" width="900" />

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
