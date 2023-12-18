---
switcher-label: Language
---

# Main

![main](https://files.realpython.com/media/Python-Main-Function_Watermarked.5b31a1de4516.jpg)
{ centered=true }

## Purpose

<note>
<b>Definition & Use</b>

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


## Syntax 

The `main` function is defined as follows:

### Pseudocode {switcher-key="Pseudocode"}

```text
main 
    // Statements
end main
```


### Main C++ {switcher-key="C++"}

```c++
int main() {
    // Statements
}
```


### Main Python {switcher-key="Python"}

```Python
def main():
    # Statements
```

### Main Java {switcher-key="Java"}

```java
public static void main(String[] args) {
    // Statements
}
```

### Main Go {switcher-key="Go"}

```go
func main() {
    // Statements
}
```






