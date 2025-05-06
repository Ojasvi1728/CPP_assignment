
---

### **1. What is the fundamental difference between procedural and object-oriented programming paradigms? Provide a brief example to illustrate.**

**Procedural Programming:**  
Procedural programming is a programming paradigm based on structured programming, where the code is executed in a step-by-step manner using procedures (or functions). The focus is on writing procedures or functions that operate on data. The key characteristics of procedural programming are:

- Code is structured into functions or procedures.
- Follows a linear top-down approach.
- Data is usually global and can be accessed by any function.
- Example languages: C, Pascal, Fortran.

**Object-Oriented Programming (OOP):**  
OOP is based on objects, which are instances of classes. It focuses on modeling real-world entities and behaviors by bundling data and related functions into classes. Key features of OOP include:

- Encapsulation: Data and methods are combined within objects.
- Abstraction: Hides implementation details and exposes only necessary functionality.
- Inheritance: New classes can inherit features from existing classes.
- Polymorphism: Objects can take multiple forms for flexible code execution.

**Example Comparison:**

_Procedural Approach:_

```cpp
#include <iostream>
using namespace std;

void displayStudent(string name, int age) {
    cout << "Student Name: " << name << ", Age: " << age << endl;
}

int main() {
    string name = "Alice";
    int age = 20;
    displayStudent(name, age);
    return 0;
}
```

Here, functions operate on the data directly.

_OOP Approach:_

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    void display() {
        cout << "Student Name: " << name << ", Age: " << age << endl;
    }
};

int main() {
    Student s1;
    s1.name = "Alice";
    s1.age = 20;
    s1.display();
    return 0;
}
```

Here, we encapsulate both the data (name, age) and behavior (`display()`) inside the `Student` class.

---

### **2. Define Object-Oriented Programming (OOP). What are its core characteristics?**

**Definition:**  
Object-Oriented Programming (OOP) is a programming paradigm that uses objects to design applications and software. Objects are instances of classes, which are blueprints defining properties and behaviors.

**Core Characteristics:**

1. **Encapsulation:** Restricting direct access to data by using private variables and providing controlled access through public methods.
2. **Abstraction:** Hiding unnecessary implementation details from the user and exposing only essential functionalities.
3. **Inheritance:** Allowing new classes to inherit properties and methods from existing classes, reducing redundancy.
4. **Polymorphism:** Enabling a function or method to behave differently based on the object it is acting upon.

---

### **3. Explain the concept of "abstraction" within the context of OOP. Why is it important?**

**Abstraction** refers to the concept of hiding complex implementation details and exposing only the necessary features of an object. It allows developers to work with higher-level functionalities without worrying about intricate details.

**Importance of Abstraction:**

- Reduces complexity in large projects.
- Improves maintainability and code readability.
- Enhances security by restricting access to implementation details.
- Helps achieve modularity, allowing independent development of components.

**Example:**

```cpp
class Car {
public:
    void start() {  
        cout << "Car started" << endl;
    }
private:
    void igniteEngine() {  
        cout << "Engine ignited" << endl;
    }
};
```

Here, the `start()` method is exposed to the user, while `igniteEngine()` is hidden, following the abstraction principle.

---

### **4. What are the benefits of using OOP over procedural programming?**

1. **Code Reusability:** Classes and objects promote reuse through inheritance, reducing redundant code.
2. **Encapsulation for Security:** Sensitive data is hidden from the outside world.
3. **Modularity:** Programs are divided into smaller parts (objects), making debugging easier.
4. **Scalability:** It is easier to add new features without modifying existing code significantly.
5. **Data Integrity:** By controlling access to data, OOP prevents accidental modifications.

---

### **5. Give a real-world example of a problem that is well-suited to be solved using an OOP approach. Explain why.**

**Example: Banking System**  
A banking system needs to manage accounts, transactions, customers, and employees.

Using OOP, we can define classes:

- `Account` (attributes: balance, account number, methods: deposit, withdraw)
- `Customer` (attributes: name, ID, address, methods: viewBalance)
- `Transaction` (attributes: transaction ID, amount, methods: processTransaction)

**Why OOP?**

- **Encapsulation:** Protects account details.
- **Inheritance:** Different types of accounts (Savings, Checking) can inherit from `Account`.
- **Polymorphism:** Multiple transaction types (credit, debit) can be processed with the same interface.

---

### **6. Define the four key principles of OOP: Encapsulation, Inheritance, Polymorphism, and Abstraction.**

6. **Encapsulation:** Restricts direct access to data and ensures it is modified only through methods.
7. **Inheritance:** Allows new classes to derive properties from existing ones, reducing code duplication.
8. **Polymorphism:** Enables methods to perform different tasks based on the object calling them.
9. **Abstraction:** Hides unnecessary details and exposes only the required functionality.

---

### **7. Explain how encapsulation helps to protect data and create modular code. Give an example using a class and its members.**

Encapsulation ensures that sensitive data is only accessible through well-defined methods.

**Example:**

```cpp
class BankAccount {
private:
    double balance;

public:
    void deposit(double amount) {
        if (amount > 0) balance += amount;
    }

    double getBalance() {
        return balance;
    }
};
```

Here, direct access to `balance` is restricted to prevent unauthorized modifications.

---

### **8. What is inheritance? How does it promote code reuse and maintainability? Provide a simple example using classes.**

**Definition:** Inheritance allows a class to acquire properties and behaviors from another class.

**Example:**

```cpp
class Animal {
public:
    void eat() { cout << "Eating..." << endl; }
};

class Dog : public Animal {
public:
    void bark() { cout << "Barking..." << endl; }
};

int main() {
    Dog d;
    d.eat();  
    d.bark();
}
```

Here, `Dog` inherits the `eat()` method from `Animal`.

---

### **9. Describe polymorphism. How does it contribute to flexibility and extensibility in software design?**

Polymorphism allows the same function to operate differently based on the input object.

**Example of Function Overloading:**

```cpp
class Math {
public:
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }
};
```

**Example of Function Overriding:**

```cpp
class Parent {
public:
    virtual void show() { cout << "Parent class" << endl; }
};

class Child : public Parent {
public:
    void show() override { cout << "Child class" << endl; }
};
```

Polymorphism enables flexible and extensible software design by allowing multiple behaviors for a single function.

---

### **10. Explain the difference between "overloading" and "overriding".**

Both overloading and overriding are part of polymorphism, but they work differently.

|Feature|Function Overloading|Function Overriding|
|---|---|---|
|**Definition**|Allows multiple functions with the same name but different parameters.|A derived class provides a new implementation of a method that is already defined in its base class.|
|**Scope**|Happens within the same class.|Happens in an inheritance relationship between a base and a derived class.|
|**Method Signature**|Must differ in the number or type of parameters.|Method signature remains the same as the base class.|
|**Return Type**|Can be different.|Must be the same.|
|**Keyword Used**|No special keyword.|`virtual` keyword is used in the base class.|
|**Example**|`int sum(int a, int b)` and `double sum(double a, double b)` in the same class.|`void show()` in a base class and `void show()` in a derived class with different functionality.|

**Example of Function Overloading:**

```cpp
class Math {
public:
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }
};
```

**Example of Function Overriding:**

```cpp
class Parent {
public:
    virtual void show() { cout << "Parent class" << endl; }
};

class Child : public Parent {
public:
    void show() override { cout << "Child class" << endl; }
};
```

---

### **11. List at least three advantages of using OOP in software development.**

1. **Code Reusability** – Inheritance allows developers to reuse existing code, reducing redundancy.
2. **Encapsulation for Data Security** – Protects data by restricting direct access.
3. **Scalability and Maintainability** – Modular design makes it easier to modify, debug, and scale.

---

### **12. Give examples of application domains where OOP is commonly used.**

- **GUI Development:** Java Swing, Qt in C++.
- **Game Development:** Unity (C#), Unreal Engine (C++).
- **Machine Learning:** TensorFlow (Python, C++).
- **Database Management:** MySQL, PostgreSQL (use OOP concepts).

---

### **13. Discuss the impact of OOP on code maintainability and reusability.**

- **Maintainability:** Modularity and encapsulation reduce dependencies, making it easy to update code.
- **Reusability:** Inheritance allows existing classes to be reused without modifying the original code.
- **Extensibility:** Polymorphism allows new functionalities to be added without breaking existing code.

Example:  
A `Vehicle` class can be extended by `Car`, `Bike`, and `Truck`, avoiding duplication of common vehicle properties.

---

### **14. How does OOP contribute to the development of large and complex software systems?**

4. **Modular Design:** Classes and objects divide software into manageable parts.
5. **Encapsulation:** Reduces the risk of accidental data modification.
6. **Extensibility:** New features can be added without affecting existing code.
7. **Collaboration:** Large teams can work on different modules without interfering with each other.

Example:  
A large e-commerce platform like Amazon uses OOP to manage different modules (Users, Orders, Products, Payments).

---

### **15. Explain the benefits of using OOP in software development.**

- **Modularity:** Components can be independently modified.
- **Security:** Encapsulation hides sensitive data.
- **Reusability:** Inheritance reduces duplicate code.
- **Flexibility:** Polymorphism allows a single interface to support multiple implementations.
- **Maintainability:** Well-structured code makes debugging easier.

---

### **16. Describe the basic structure of a C++ program. What are the essential components?**

A basic C++ program consists of:

8. **Preprocessor Directives** – `#include<iostream>` to include libraries.
9. **Namespace Declaration** – `using namespace std;` to avoid name conflicts.
10. **Main Function** – `int main()` is the entry point.
11. **Statements and Expressions** – Code logic inside `{}`.
12. **Return Statement** – `return 0;` indicates successful execution.

Example:

```cpp
using namespace std;

int main() {
    cout << "Hello, World!";
    return 0;
}
```

---

### **17. Explain the purpose of namespaces in C++. How do they help to avoid naming conflicts?**

A **namespace** is a container for identifiers to prevent name conflicts.

**Why Use Namespaces?**

- Avoids clashes between variables/functions from different libraries.
- Groups related functionalities under a single name.

Example:

```cpp
namespace A {
    void display() { cout << "Namespace A" << endl; }
}

namespace B {
    void display() { cout << "Namespace B" << endl; }
}

int main() {
    A::display();
    B::display();
    return 0;
}
```

---

### **18. What are identifiers in C++? What rules must be followed when creating them?**

Identifiers are names for variables, functions, arrays, etc.

**Rules for Identifiers:**

- Must begin with a letter (A-Z, a-z) or an underscore (_).
- Cannot use reserved keywords.
- Case-sensitive.
- Should be meaningful.

Example:

```cpp
int myVar;   // Valid
int 2ndValue; // Invalid (cannot start with a number)
```

---

### **19. What are the differences between variables and constants in C++? How are they declared?**

|Feature|Variables|Constants|
|---|---|---|
|**Definition**|Store data that can change during execution.|Store fixed values that cannot be modified.|
|**Declaration**|`int x = 5;`|`const int x = 5;`|
|**Mutability**|Can be changed.|Cannot be changed.|

Example:

```cpp
const double pi = 3.14159;  // Constant
int age = 20;  // Variable
```

---

### **20. Explain how to use control structures (e.g., if-else, for, while) to control the flow of execution in a C++ program. Provide a simple code example.**

Control structures help determine the flow of execution based on conditions.

**1. If-Else Statement:**

```cpp
int num = 10;
if (num > 0)
    cout << "Positive";
else
    cout << "Negative";
```

**2. For Loop (Iteration with a known count):**

```cpp
for (int i = 0; i < 5; i++) {
    cout << i << " ";
}
```

**3. While Loop (Iteration with an unknown count):**

```cpp
int i = 0;
while (i < 5) {
    cout << i << " ";
    i++;
}
```

---