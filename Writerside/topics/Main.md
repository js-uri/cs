---
switcher-label: Language
---

# Main &amp; Command Line Arguments

![main](https://files.realpython.com/media/Python-Main-Function_Watermarked.5b31a1de4516.jpg)
{ centered=true }

## Main Purpose

<note>
<b>Definition &amp; Use</b>

The `main` function is the entry point of a program. It is the first function to be called when a program starts execution. The `main` function is the only function that is required to be present in a program. All other functions can be defined and called from within the `main` function. 
</note>

<table>
<tr>
<td>Pros</td><td>Cons</td>
</tr>
<tr>
<td>
<deflist collapsible="true">
<def title="Organization">
The `main` function provides a central location for organizing and structuring the code of a program.
</def>
<def title="Reusability">
The `main` function can be used to call other functions, enabling code reuse.
</def>
<def title="Execution">
The `main` function is the first function to be executed when a program starts.
</def>
<def title="Testing">
The `main` function can be used to test other functions.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true">
<def title="Complexity">
The `main` function can become complex and difficult to understand if it contains too much code.
</def>
<def title="Coupling">
The `main` function can become tightly coupled with other functions if it calls too many functions.
</def>
<def title="Testing">
The `main` function can be difficult to test if it calls too many functions.
</def>
</deflist>
</td>
</tr>
</table>


## Main Syntax 

The `main` function is defined as follows:

### Pseudocode {switcher-key="Pseudocode"}

```text
main 
    // Statements
end main
```


### Main C++ {switcher-key="C++"}

<video src="https://youtu.be/imNlJohlLPk?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="C++">
</video>

```c++
int main() {
    // Statements
}
```


### Main Python {switcher-key="Python"}

<video src="https://youtu.be/lVUOrPunRxQ?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="Python">
</video>

```Python
def main():
    # Statements
```

### Main Java {switcher-key="Java"}

<video src="https://youtu.be/P-_Nzi_mCRo?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="Java">
</video>

```java
public static void main(String[] args) {
    // Statements
}
```

### Main Go {switcher-key="Go"}

<video src="https://youtu.be/8gqQhihZ3hY?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="Go">
</video>

```go
func main() {
    // Statements
}
```

## Command Line Arguments (CLAs)

### CLAs Defined

<note>
<b>Definition &amp; Use</b>

Command line arguments are strings of text that are passed to a program when it is started. They are used to provide input to a program.
</note>

## CLA Syntax

Command line arguments are passed to a program as follows:

### CLA C++ {switcher-key="C++"}

<video src="https://youtu.be/decAHMKIo_A?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="C++">

</video>

    ```c++
    int main(int argc, char* argv[]) {
        // Statements
    }
    ```

### CLA Python {switcher-key="Python"}

<video src="https://youtu.be/rJCl7t3IIbA?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="Python">
</video>

```Python
def main(argv):
    # Statements
```

### CLA Java {switcher-key="Java"}

<video src="https://youtu.be/Up17-azeuyE?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="Java">
</video>

```java
public static void main(String[] args) {
    // Statements
}
```

### CLA Go {switcher-key="Go"}

<video src="https://youtu.be/pISqGhRB3Jg?feature=shared" 
       preview-src="hero_main.jpeg"
       width="900"
       controls 
       preload 
       switcher-key="Go">
</video>

```go
func main() {
    // Statements
}
```



