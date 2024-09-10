---
switcher-label: Language
---

# C++ Review

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

<video src="https://youtu.be/2BP8NhxjrO0?feature=shared" preview-src="oop.jpeg" mini-player="true" width="900" />

## Example

> A car rental company needs to manage their fleet of cars. Each car has the following attributes: make, model, year, rental price per day, and availability status (whether the car is currently rented or available). The company wants a system where they can:
> 
> - Add a new car to the fleet.
> - Display information about all cars.
> - Check availability of a specific car by its make and model.
> - Update the availability of a car when it is rented out or returned.

### Breakdown

**Class Design:**
- A `Car` class will encapsulate the attributes and behaviors of a car.
- Attributes: `make`, `model`, `year`, `rentalPrice`, and `available`.
- Behaviors: Adding new cars, displaying details, checking availability, and updating the rental status.

**Core Functionalities:**
- The fleet will be stored in a collection (e.g., a vector of Car objects).
- Functions for adding cars, displaying the fleet, checking availability, and updating the status will be implemented.

### Pseudocode

```
Class Car:
    Attributes:
        - make (string)
        - model (string)
        - year (int)
        - rentalPrice (double)
        - available (bool)
    
    Methods:
        - Constructor to initialize car details
        - displayInfo() to display the car details
        - isAvailable() to check if the car is available
        - rentOut() to mark the car as rented
        - returnCar() to mark the car as available again

Function to add new car:
    Create a new Car object with provided details
    Add the Car object to the fleet

Function to display all cars:
    For each Car in the fleet, call displayInfo()

Function to check availability by make and model:
    Iterate through the fleet and check if any car matches the make and model
    If a match is found, return the availability status

Function to update rental status:
    Find the car by make and model
    If available, mark as rented out
    If rented, mark as available again
```

### Source Code

#### Header File : Car.h

A header file in C++ is a file that contains declarations of classes, functions, variables, and other entities that can be used in multiple source files. Header files typically have a `.h` extension and are included in source files using the `#include` directive. They help in organizing code, promoting reusability, and reducing redundancy by providing a central location for common declarations.

```c++
// Declaration of the Car class. It defines the class's attributes, methods, and constructor prototypes.

#ifndef CAR_H
#define CAR_H

#include <string>

class Car {
private:
    std::string make;
    std::string model;
    int year;
    double rentalPrice;
    bool available;

public:
    // Constructor
    Car(std::string mk, std::string mdl, int yr, double price, bool avail = true);

    // Method to display car information
    void displayInfo() const;

    // Method to check if the car is available
    bool isAvailable() const;

    // Method to rent the car out
    void rentOut();

    // Method to return the car
    void returnCar();

    // Method to check if a car matches a given make and model
    bool matches(std::string mk, std::string mdl) const;
};

#endif // CAR_H
```

#### Class Implementation : Car.cpp

```c++
// Implements the functions of the Car class. It includes Car.h to link the function prototypes with their implementations.

#include "Car.h"
#include <iostream>

// Constructor implementation
Car::Car(std::string mk, std::string mdl, int yr, double price, bool avail)
    : make(mk), model(mdl), year(yr), rentalPrice(price), available(avail) {}

// Method to display car information
void Car::displayInfo() const {
    std::cout << "Make: " << make << ", Model: " << model
              << ", Year: " << year << ", Rental Price: $" << rentalPrice
              << " per day, " << (available ? "Available" : "Rented") << std::endl;
}

// Method to check if the car is available
bool Car::isAvailable() const {
    return available;
}

// Method to rent the car out
void Car::rentOut() {
    if (available) {
        available = false;
        std::cout << make << " " << model << " has been rented out.\n";
    } else {
        std::cout << make << " " << model << " is already rented.\n";
    }
}

// Method to return the car
void Car::returnCar() {
    if (!available) {
        available = true;
        std::cout << make << " " << model << " has been returned and is now available.\n";
    } else {
        std::cout << make << " " << model << " is already available.\n";
    }
}

// Method to check if a car matches a given make and model
bool Car::matches(std::string mk, std::string mdl) const {
    return (make == mk && model == mdl);
}
```

#### Main Program : main.cpp

```c++
#include "Car.h"
#include <iostream>
#include <vector>
#include <string>

// Program logic, which uses the Car class to manage the fleet, is contained here. It includes Car.h to use the Car class and its methods.


// Function to add a new car to the fleet
void addCar(std::vector<Car>& fleet, std::string make, std::string model, int year, double price) {
    Car newCar(make, model, year, price);
    fleet.push_back(newCar);
    std::cout << "New car added to the fleet: " << make << " " << model << std::endl;
}

// Function to display all cars in the fleet
void displayFleet(const std::vector<Car>& fleet) {
    for (const auto& car : fleet) {
        car.displayInfo();
    }
}

// Function to check the availability of a specific car
void checkAvailability(const std::vector<Car>& fleet, std::string make, std::string model) {
    for (const auto& car : fleet) {
        if (car.matches(make, model)) {
            std::cout << make << " " << model << " is " 
                      << (car.isAvailable() ? "available." : "rented.") << std::endl;
            return;
        }
    }
    std::cout << make << " " << model << " is not in the fleet.\n";
}

// Function to update the rental status of a car
void updateRentalStatus(std::vector<Car>& fleet, std::string make, std::string model, bool renting) {
    for (auto& car : fleet) {
        if (car.matches(make, model)) {
            if (renting) {
                car.rentOut();
            } else {
                car.returnCar();
            }
            return;
        }
    }
    std::cout << "No car found with make " << make << " and model " << model << ".\n";
}

int main() {
    std::vector<Car> fleet;

    // Adding cars to the fleet
    addCar(fleet, "Toyota", "Corolla", 2020, 55.00);
    addCar(fleet, "Ford", "Mustang", 2019, 120.00);
    addCar(fleet, "Honda", "Civic", 2021, 60.00);

    // Displaying all cars in the fleet
    std::cout << "\nFleet information:\n";
    displayFleet(fleet);

    // Checking availability of a specific car
    std::cout << "\nChecking availability of Honda Civic:\n";
    checkAvailability(fleet, "Honda", "Civic");

    // Renting out a car
    std::cout << "\nRenting out Honda Civic:\n";
    updateRentalStatus(fleet, "Honda", "Civic", true);

    // Checking availability after renting
    std::cout << "\nChecking availability again of Honda Civic:\n";
    checkAvailability(fleet, "Honda", "Civic");

    // Returning the car
    std::cout << "\nReturning Honda Civic:\n";
    updateRentalStatus(fleet, "Honda", "Civic", false);

    return 0;
}

// Compile && Run Commands
// g++ -Wall -g main.cpp Car.cpp -o main && ./main
```

### Class Aspects

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="encapsulation.jpeg" mini-player="true" width="900" />

#### Encapsulation

Encapsulation refers to the bundling of data (variables) and methods (functions) that operate on that data into a single unit or class. It also controls the access to that data by restricting direct access to some components and allowing controlled access through public methods. This promotes data hiding and protects the internal state of an object from unintended interference.

Example:

In the `Car` class, the attributes like `make`, `model`, `year`, `rentalPrice`, and `available` are encapsulated within the class. They are marked as private to hide them from outside the class. The access to these attributes is controlled through public methods like `displayInfo()`, `isAvailable()`, `rentOut()`, and `returnCar()`.

```c++
class Car {
private:
    string make;
    string model;
    int year;
    double rentalPrice;
    bool available;

public:
    void displayInfo() const;
    bool isAvailable() const;
    void rentOut();
    void returnCar();
};
```

Encapsulation ensures that the internal details of the car's state (whether it's rented or available, or its rental price) can only be modified through well-defined interfaces (`rentOut()`, `returnCar()`), protecting the integrity of the object.

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="abstraction.jpeg" mini-player="true" width="900" />

#### Abstraction

Abstraction is the concept of hiding complex details and exposing only the essential parts of an object to the outside world. It simplifies interaction with objects by allowing users to focus on what an object does rather than how it does it.

Example :

In the `Car` class, the internal workings of how a car is rented out or returned are abstracted away. The user of the class only needs to call the methods `rentOut()` and `returnCar()` without worrying about the details of how the availability status is updated.

```c++
// Method to rent the car out
void Car::rentOut() {
    if (available) {
        available = false;
        std::cout << make << " " << model << " has been rented out.\n";
    } else {
        std::cout << make << " " << model << " is already rented.\n";
    }
}

// Method to return the car
void Car::returnCar() {
    if (!available) {
        available = true;
        std::cout << make << " " << model << " has been returned and is now available.\n";
    } else {
        std::cout << make << " " << model << " is already available.\n";
    }
}
```

The abstraction here allows the user to rent or return cars by calling simple methods, hiding the underlying implementation details like how the available status is updated.

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="inheritance.jpeg" mini-player="true" width="900" />

#### Inheritance

Inheritance is a mechanism by which one class (child or derived class) inherits the properties and behaviors (methods) of another class (parent or base class). This allows for code reuse and the creation of more specific subclasses from general ones.

Example:

Although the provided example does not demonstrate inheritance explicitly, suppose we extend the `Car` class to include different types of cars like `LuxuryCar` or `SUV`, we could use inheritance:

```c++
class LuxuryCar : public Car {
private:
    bool chauffeurService;

public:
    LuxuryCar(string mk, string mdl, int yr, double price, bool chauffeur = false)
        : Car(mk, mdl, yr, price), chauffeurService(chauffeur) {}

    void displayLuxuryFeatures() const {
        cout << (chauffeurService ? "Includes chauffeur service.\n" : "No chauffeur service.\n");
    }
};
```

`LuxuryCar` is inheriting the attributes and behaviors of the `Car` class, and it also adds a new feature, `chauffeurService`. This is an example of how inheritance allows us to build more specific versions of a base class.

<video src="https://youtu.be/3z3l3v8_7uI?feature=shared" preview-src="polymorphism.jpeg" mini-player="true" width="900" />

#### Polymorphism

Polymorphism is the ability of different classes to be treated as instances of the same base class. The most common types are:

- Compile-time polymorphism (e.g., method overloading).
- Run-time polymorphism (e.g., method overriding using inheritance).
- 
Polymorphism allows one interface to be used for different underlying data types, letting a function handle different types of objects.

Example:

In the context of the car rental system, suppose we extend the example to use polymorphism. We could have a `Car` class with a virtual function `displayInfo()`, and derived classes like `LuxuryCar` and `SUV` that override `displayInfo()`.

```c++
class Car {
public:
    virtual void displayInfo() const {
        cout << "Basic Car Info\n";
    }
};

class LuxuryCar : public Car {
public:
    void displayInfo() const override {
        cout << "Luxury Car with advanced features.\n";
    }
};

void showCarDetails(Car* car) {
    car->displayInfo();
}

int main() {
    Car basicCar;
    LuxuryCar luxuryCar;

    showCarDetails(&basicCar);   // Output: Basic Car Info
    showCarDetails(&luxuryCar);  // Output: Luxury Car with advanced features
}
```

The function `showCarDetails()` uses run-time polymorphism (virtual function `displayInfo()`) to call the appropriate `displayInfo()` method based on the actual object type (`Car` or `LuxuryCar`), despite receiving a pointer of type `Car*`.


