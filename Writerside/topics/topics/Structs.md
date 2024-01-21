---
switcher-label: Language
---

# Structs

<procedure switcher-key="C++">
<video src="https://youtu.be/IW16boBvQpc?feature=shared" preview-src="structs.jpeg" mini-player="true" width="900" /> 
</procedure>
<procedure switcher-key="Python">
<video src="https://youtu.be/gViM3ZuDQrw?feature=shared" preview-src="structs.jpeg" mini-player="true" width="900" /> 
</procedure>
<procedure switcher-key="Java">
<video src="https://youtu.be/aITdnsUTeek?feature=shared" preview-src="structs.jpeg" mini-player="true" width="900" /> 
</procedure>
<procedure switcher-key="Go">
<video src="https://youtu.be/WsciIWP-8DQ?feature=shared" preview-src="structs.jpeg" mini-player="true" width="900" />
</procedure>


## Overview

<note>

**Definition:**

Structs are a way to create your own data types. They are similar to classes in that they can contain data members and functions, but they are different in that they cannot inherit from other structs or classes, and they do not have access modifiers. Structs are useful for grouping data together to create a new data type.
</note>

## Syntax

### Creating New Data Types

Structs are used to create new data types. For example, you could create a struct called `Person` that contains the data members `name`, `age`, and `height`. You could then create a variable of type `Person` called `person1` and assign values to its data members.

<procedure switcher-key="C++">
<b>C++</b>

```c++  
struct Person {
    string name;
    int age;
    double height;
};

int main() {
    Person person1;
    person1.name = "John";
    person1.age = 20;
    person1.height = 5.8;
    return 0;
}
```

<br/>

```text
// Output

John
20
5.8
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python
class Person:
    def __init__(self, name, age, height):
        self.name = name
        self.age = age
        self.height = height
        
person1 = Person("John", 20, 5.8)
```

<br/>

```text
// Output

John
20
5.8
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java
public class Person {
    String name;
    int age;
    double height;
}

public class Main {
    public static void main(String[] args) {
        Person person1 = new Person();
        person1.name = "John";
        person1.age = 20;
        person1.height = 5.8;
    }
}
```

<br/>

```text
// Output

John
20
5.8
```
{ collapsible="true" }

</procedure>

<procedure switcher-key="Go">
<b>Go</b>

```go
type Person struct {
    name string
    age int
    height float64
}

func main() {
    person1 := Person{"John", 20, 5.8}
}
```

<br/>

```text
// Output

John
20
5.8
```
{ collapsible="true" }

</procedure>



### Creating Arrays of Structs

Structs can also be used to create arrays of structs. For example, you could create an array of `Person` structs called `people` and assign values to its data members.

<procedure switcher-key="C++">
<b>C++</b>

```c++
struct Person {
    string name;
    int age;
    double height;
};

int main() {
    Person people[3];
    people[0].name = "John";
    people[0].age = 20;
    people[0].height = 5.8;
    people[1].name = "Mary";
    people[1].age = 18;
    people[1].height = 5.5;
    people[2].name = "Bob";
    people[2].age = 22;
    people[2].height = 6.0;
    return 0;
}
```
</procedure>

<procedure switcher-key="Python">
<b>Python</b>

```python
class Person:
    def __init__(self, name, age, height):
        self.name = name
        self.age = age
        self.height = height
        
people = [Person("John", 20, 5.8), Person("Mary", 18, 5.5), Person("Bob", 22, 6.0)]
```

</procedure>

<procedure switcher-key="Java">
<b>Java</b>

```java
public class Person {
    String name;
    int age;
    double height;
}

public class Main {
    public static void main(String[] args) {
        Person[] people = new Person[3];
        people[0] = new Person();
        people[0].name = "John";
        people[0].age = 20;
        people[0].height = 5.8;
        people[1] = new Person();
        people[1].name = "Mary";
        people[1].age = 18;
        people[1].height = 5.5;
        people[2] = new Person();
        people[2].name = "Bob";
        people[2].age = 22;
        people[2].height = 6.0;
    }
}
```

</procedure>

<procedure switcher-key="Go">

<b>Go</b>

```go
type Person struct {
    name string
    age int
    height float64
}

func main() {
    people := [3]Person{{"John", 20, 5.8}, {"Mary", 18, 5.5}, {"Bob", 22, 6.0}}
}
```

</procedure>



### Creating Linked Lists of Structs

Structs can also be used to create linked lists. For example, you could create a linked list of `Person` structs called `people` and assign values to its data members.

<procedure switcher-key="C++">
<b>C++</b>

```c++
struct Person {
    string name;
    int age;
    double height;
    Person *next;
};

int main() {
    Person *people = new Person;
    people->name = "John";
    people->age = 20;
    people->height = 5.8;
    people->next = new Person;
    people->next->name = "Mary";
    people->next->age = 18;
    people->next->height = 5.5;
    people->next->next = new Person;
    people->next->next->name = "Bob";
    people->next->next->age = 22;
    people->next->next->height = 6.0;
    return 0;
}
```
</procedure>

<procedure switcher-key="Python">

<b>Python</b>

```python
class Person:
    def __init__(self, name, age, height):
        self.name = name
        self.age = age
        self.height = height
        self.next = None

people = Person("John", 20, 5.8)
people.next = Person("Mary", 18, 5.5)
people.next.next = Person("Bob", 22, 6.0)
```

</procedure>

<procedure switcher-key="Java">

<b>Java</b>

```java
public class Person {
    String name;
    int age;
    double height;
    Person next;
}

public class Main {
    public static void main(String[] args) {
        Person people = new Person();
        people.name = "John";
        people.age = 20;
        people.height = 5.8;
        people.next = new Person();
        people.next.name = "Mary";
        people.next.age = 18;
        people.next.height = 5.5;
        people.next.next = new Person();
        people.next.next.name = "Bob";
        people.next.next.age = 22;
        people.next.next.height = 6.0;
    }
}
```

</procedure>

<procedure switcher-key="Go">

<b>Go</b>

```go
type Person struct {
    name string
    age int
    height float64
    next *Person
}

func main() {
    people := &Person{"John", 20, 5.8, &Person{"Mary", 18, 5.5, &Person{"Bob", 22, 6.0, nil}}}
}
```

</procedure>


