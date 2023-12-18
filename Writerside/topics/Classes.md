---
switcher-label: Language
---

# Classes

<video src="https://youtu.be/SiBw7os-_zI?feature=shared" preview-src="oop1.jpeg" mini-player="true" width="900" />

## Overview

<note>
<p>Definition</p>

<a href="https://youtu.be/m_MQYyJpIjg">Object-Oriented Programming</a> is a programming paradigm that revolves around the concept of objects, which are instances of classes. Classes are user-defined data types that encapsulate data and behavior. They allow us to model real-world entities and their interactions through the use of attributes (data) and methods (functions).

<i>Note: not all languages are built for OOP. But OOP can be injected into your code through a little creative programming</i>
</note>

<table>
<tr>
<td>Pros</td><td>Cons</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Modularity">Code can be organized into self-contained objects, making it easier to understand and maintain.</def>
<def title="Reusability">Classes and objects promote code reuse, reducing redundant implementations.</def>
<def title="Encapsulation">Data hiding ensures that the internal representation of an object is hidden, and access to it is restricted to methods, promoting security and data integrity.</def>
<def title="Inheritance">Inheritance enables the creation of hierarchies and facilitates code sharing and extension.</def>
<def title="Polymorphism">Polymorphism allows objects of different classes to be treated as objects of a common superclass, promoting flexibility and generality.</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Complexity">OOP can introduce additional complexity, especially for smaller projects where simpler paradigms might suffice.</def>
<def title="Overhead">It can lead to performance overhead due to dynamic dispatch and object creation.</def>
<def title="Learning Curve">Understanding and mastering OOP concepts can be challenging for beginners.</def>
</deflist>
</td>
</tr>
</table>

### Use Cases

<tip>
<p>OOP is widely used in various domains, such as software development, game development, simulation, and more. It helps in creating modular, maintainable, and extensible code.</p>
</tip>

## Syntax

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

<video src="https://youtu.be/XHjuHPn8QKY?feature=shared" preview-src="oop.jpeg" mini-player="true" width="900" />

<br/>

```text
CLASS Animal:
    ATTRIBUTES:
        name
        age
    METHODS:
        constructor(name, age)
        make_sound()
    END CLASS

FUNCTION main():
    animal1 = Animal("Buddy", 3)
    animal1.make_sound()
    animal2 = Animal("Charlie", 5)
    animal2.make_sound()
END FUNCTION
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

<video src="https://youtu.be/2BP8NhxjrO0?feature=shared" preview-src="oop.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <iostream>
#include <string>

using namespace std;

class Animal {
    private:
        string name;
        int age;
    public:
        Animal(string name, int age) {
            this->name = name;
            this->age = age;
        }
        void make_sound() {
            cout << "Grr..." << endl;
        }
};

int main() {
    Animal animal1("Buddy", 3);
    animal1.make_sound();
    Animal animal2("Charlie", 5);
    animal2.make_sound();
    return 0;
}
```
<br/>

```text
// Output:

Grr...
Grr...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

<video src="https://youtu.be/f0TrMH9s-VE?feature=shared" preview-src="oop.jpeg" mini-player="true" width="900" />

<br/>

```python
class Animal:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def make_sound(self):
        print("Grr...")

animal1 = Animal("Buddy", 3)
animal1.make_sound()
animal2 = Animal("Charlie", 5)
animal2.make_sound()
```

<br/>

```text
# Output:

Grr...
Grr...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

<video src="https://youtu.be/IUqKuGNasdM?feature=shared" preview-src="oop.jpeg" mini-player="true" width="900" />

<br/>

```java
class Animal {
    private String name;
    private int age;
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public void make_sound() {
        System.out.println("Grr...");
    }
}   

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Animal("Buddy", 3);
        animal1.make_sound();
        Animal animal2 = new Animal("Charlie", 5);
        animal2.make_sound();
    }
}
```

<br/>

```text
// Output:

Grr...
Grr...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

<video src="https://youtu.be/sPX6ORiyd0o?feature=shared" preview-src="oop.jpeg" mini-player="true" width="900" />

<br/>

<note>
<p>You may notice the structure below is a struct, not a class. Go is not a Object-Oriented Programming language but we still have ways to manipulate the language to work in an O-O way...</p>
</note>

<br/>

```go
package main

import "fmt"

type Animal struct {
    name string
    age int
}

func (a Animal) make_sound() {
    fmt.Println("Grr...")
}

func main() {
    animal1 := Animal{"Buddy", 3}
    animal1.make_sound()
    animal2 := Animal{"Charlie", 5}
    animal2.make_sound()
}
```

<br/>

```text
// Output:

Grr...
Grr...
```
{ collapsible="true" }

</procedure>



