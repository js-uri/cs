---
switcher-label: Language
---

# Classes

<video src="https://youtu.be/SiBw7os-_zI?feature=shared" preview-src="oop1.jpeg" mini-player="true" width="900" />

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



## Inheritance

<note>
<p>Definition</p>

Inheritance is a mechanism in OOP that allows a new class to inherit properties and methods from an existing class. The existing class is called the base class or parent class, and the new class is called the derived class or child class. Inheritance promotes code reuse and facilitates the creation of hierarchies.
</note>

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="inheritance.jpeg" mini-player="true" width="900" />

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

CLASS Dog INHERITS Animal:
    METHODS:
        constructor(name, age, breed)
        make_sound()
    END CLASS

FUNCTION main():
    dog1 = Dog("Buddy", 3, "Golden Retriever")
    dog1.make_sound()
    dog2 = Dog("Charlie", 5, "Labrador")
    dog2.make_sound()
END FUNCTION
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="inheritance.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <iostream>
#include <string>

using namespace std;


class Animal {
    protected:
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

class Dog : public Animal {
    private:
        string breed;
    public:
        Dog(string name, int age, string breed) : Animal(name, age) {
            this->breed = breed;
        }
        void make_sound() {
            cout << "Woof..." << endl;
        }
};

int main() {
    Dog dog1("Buddy", 3, "Golden Retriever");
    dog1.make_sound();
    Dog dog2("Charlie", 5, "Labrador");
    dog2.make_sound();
    return 0;
}
```
<br/>

```text
// Output:

Woof...
Woof...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="inheritance.jpeg" mini-player="true" width="900" />

<br/>

```python
class Animal:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def make_sound(self):
        print("Grr...")

class Dog(Animal):
    def __init__(self, name, age, breed):
        super().__init__(name, age)
        self.breed = breed
    def make_sound(self):
        print("Woof...")

dog1 = Dog("Buddy", 3, "Golden Retriever")
dog1.make_sound()
dog2 = Dog("Charlie", 5, "Labrador")
dog2.make_sound()
```

<br/>

```text
# Output:

Woof...
Woof...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="inheritance.jpeg" mini-player="true" width="900" />

<br/>

```java
class Animal {
    protected String name;
    protected int age;
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public void make_sound() {
        System.out.println("Grr...");
    }
}

class Dog extends
Animal {
    private String breed;
    public Dog(String name, int age, String breed) {
        super(name, age);
        this.breed = breed;
    }
    public void make_sound() {
        System.out.println("Woof...");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog("Buddy", 3, "Golden Retriever");
        dog1.make_sound();
        Dog dog2 = new Dog("Charlie", 5, "Labrador");
        dog2.make_sound();
    }
}
```

<br/>

```text
// Output:

Woof...
Woof...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="composition.jpeg" mini-player="true" width="900" />

<br/>

<note>
<p>Go does not support inheritance in the traditional sense. Instead, it uses composition to achieve similar results.</p>
</note>

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

type Dog struct {
    animal Animal
    breed string
}

func (d Dog) make_sound() {
    fmt.Println("Woof...")
}

func main() {
    dog1 := Dog{Animal{"Buddy", 3}, "Golden Retriever"}
    dog1.make_sound()
    dog2 := Dog{Animal{"Charlie", 5}, "Labrador"}
    dog2.make_sound()
}
```

<br/>

```text
// Output:

Woof...
Woof...
```
{ collapsible="true" }

</procedure>

## Polymorphism

<note>
<p>Definition</p>

Polymorphism is a feature of OOP that allows objects of different classes to be treated as objects of a common superclass. It promotes flexibility and generality by enabling the use of a single interface to represent different data types and objects.

Polymorphism can be achieved through method overloading and method overriding.
</note>

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="polymorphism.jpeg" mini-player="true" width="900" />

<br/>

```text
CLASS Animal:
    METHODS:
        make_sound()
    END CLASS

CLASS Dog INHERITS Animal:
    METHODS:
        make_sound()
    END CLASS

CLASS Cat INHERITS Animal:
    METHODS:
        make_sound()
    END CLASS

FUNCTION main():
    animal1 = Dog()
    animal1.make_sound()
    animal2 = Cat()
    animal2.make_sound()
END FUNCTION
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="polymorphism.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <iostream>
#include <string>
using namespace std;

class Animal {
    public:
        virtual void make_sound() {
            cout << "Grr..." << endl;
        }
};

class Dog : public Animal {
    public:
        void make_sound() {
            cout << "Woof..." << endl;
        }
};

class Cat : public Animal {
    public:
        void make_sound() {
            cout << "Meow..." << endl;
        }
};

int main() {
    Animal *animal1 = new Dog();
    animal1->make_sound();
    Animal *animal2 = new Cat();
    animal2->make_sound();
    return 0;
}
```

<br/>

```text
// Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="polymorphism.jpeg" mini-player="true" width="900" />

<br/>

```python
class Animal:
    def make_sound(self):
        print("Grr...")

class Dog(Animal):
    def make_sound(self):
        print("Woof...")

class Cat(Animal):
    def make_sound(self):
        print("Meow...")

animal1 = Dog()
animal1.make_sound()
animal2 = Cat()
animal2.make_sound()
```

<br/>

```text
# Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="polymorphism.jpeg" mini-player="true" width="900" />

<br/>

```java
class Animal {
    public void make_sound() {
        System.out.println("Grr...");
    }
}

class Dog extends
Animal {
    public void make_sound() {
        System.out.println("Woof...");
    }
}

class Cat extends
Animal {
    public void make_sound() {
        System.out.println("Meow...");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Dog();
        animal1.make_sound();
        Animal animal2 = new Cat();
        animal2.make_sound();
    }
}
```

<br/>

```text
// Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="polymorphism.jpeg" mini-player="true" width="900" />

<br/>

<note>

<p>Go does not support inheritance in the traditional sense. Instead, it uses composition to achieve similar results.</p>

</note>

```go
package main
import "fmt"

type Animal interface {
    make_sound()
}

type Dog struct {
}

    
func (d Dog) make_sound() {
    fmt.Println("Woof...")
}

type Cat struct {
}

func (c Cat) make_sound() {
    fmt.Println("Meow...")
}

func main() {
    var animal1 Animal = Dog{}
    animal1.make_sound()
    var animal2 Animal = Cat{}
    animal2.make_sound()
}
```

<br/>

```text
// Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

## Encapsulation

<note>
<p>Definition</p>

Encapsulation is a fundamental principle of OOP that restricts access to certain components of an object, such as attributes and methods, to prevent unauthorized access and modification. It promotes security, data integrity, and modularity by hiding the internal representation of an object and exposing only the necessary functionality.

Encapsulation is achieved through access specifiers, such as public, private, and protected, which control the visibility of components.
</note>

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="encapsulation.jpeg" mini-player="true" width="900" />

<br/>

```text
CLASS Animal:
    ATTRIBUTES:
        name (private)
        age (private)
    METHODS:
        constructor(name, age)
        make_sound()
    END CLASS
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="encapsulation.jpeg" mini-player="true" width="900" />

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
    return 0;
}
```

<br/>

```text
// Output:

Grr...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="encapsulation.jpeg" mini-player="true" width="900" />

<br/>

```python
class Animal:
    def __init__(self, name, age):
        self.__name = name
        self.__age = age
    def make_sound(self):
        print("Grr...")

animal1 = Animal("Buddy", 3)
animal1.make_sound()
```

<br/>

```text
# Output:

Grr...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="encapsulation.jpeg" mini-player="true" width="900" />

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
    }
}
```

<br/>

```text

// Output:

Grr...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="encapsulation.jpeg" mini-player="true" width="900" />

<br/>

<note>

<p>Go does not support access specifiers like public, private, and protected. Instead, it uses naming conventions to achieve encapsulation.</p>
</note>

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
}
```

<br/>

```text
// Output:

Grr...
```
{ collapsible="true" }

</procedure>

## Abstraction

<note>
<p>Definition</p>

Abstraction is a fundamental principle of OOP that focuses on the essential features of an object while hiding the irrelevant details. It promotes modularity, reusability, and maintainability by allowing the creation of abstract classes and methods that define the structure and behavior of objects without specifying their implementation.

Abstraction is achieved through abstract classes and methods, which cannot be instantiated and must be implemented by derived classes.

</note>

<procedure switcher-key="Pseudocode">
<b>Pseudocode</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="abstraction.jpeg" mini-player="true" width="900" />

<br/>

```text
CLASS Animal:
    METHODS:
        make_sound()
    END CLASS
```

</procedure>

<procedure switcher-key="C++">
<b>C++</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="abstraction.jpeg" mini-player="true" width="900" />

<br/>

```c++
#include <iostream>
#include <string>
using namespace std;

class Animal {
    public:
        virtual void make_sound() = 0;
};

class Dog : public Animal {
    public:
        void make_sound() {
            cout << "Woof..." << endl;
        }
};

class Cat : public Animal {
    public:
        void make_sound() {
            cout << "Meow..." << endl;
        }
};

int main() {
    Animal *animal1 = new Dog();
    animal1->make_sound();
    Animal *animal2 = new Cat();
    animal2->make_sound();
    return 0;
}
```

<br/>

```text
// Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="abstraction.jpeg" mini-player="true" width="900" />

<br/>

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        print("Woof...")

class Cat(Animal):
    def make_sound(self):
        print("Meow...")

animal1 = Dog()
animal1.make_sound()
animal2 = Cat()
animal2.make_sound()
```

<br/>

```text
# Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="abstraction.jpeg" mini-player="true" width="900" />

<br/>

```java
abstract class Animal {
    public abstract void make_sound();
}

class Dog extends
Animal {
    public void make_sound() {
        System.out.println("Woof...");
    }
}

class Cat extends
Animal {
    public void make_sound() {
        System.out.println("Meow...");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Dog();
        animal1.make_sound();
        Animal animal2 = new Cat();
        animal2.make_sound();
    }
}
```

<br/>

```text
// Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="abstraction.jpeg" mini-player="true" width="900" />

<br/>

<note>

<p>Go does not support abstract classes and methods. Instead, it uses interfaces to achieve similar results.</p>

</note>

```go
package main
import "fmt"

type Animal interface {
    make_sound()
}

type Dog struct {
}

func (d Dog) make_sound() {
    fmt.Println("Woof...")
}

type Cat struct {
}

func (c Cat) make_sound() {
    fmt.Println("Meow...")
}

func main() {
    var animal1 Animal = Dog{}
    animal1.make_sound()
    var animal2 Animal = Cat{}
    animal2.make_sound()
}
``` 

<br/>

```text
// Output:

Woof...

Meow...
```
{ collapsible="true" }

</procedure>



