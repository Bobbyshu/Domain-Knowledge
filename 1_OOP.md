# OOP & SOLID Principles

### 1. Polymorphism

- Different implementations share the same interface
- Example:
- ```
  List<Integer> list = new ArrayList<>();
  List<Integer> list2 = new Linkedlist<>();
  ```

### 2. SOLID Principles

 **Single Responsibility Principle (SRP)**

- A class should have **only one reason to change**.

- Each class handles one functionality.

**Open/Closed Principle (OCP)**

- **Open to extension**, **closed to modification**.

- Add new features by extending existing code, not changing it.

**Liskov Substitution Principle (LSP)**

- Subclasses should be substitutable for their parent classes.

- Derived class must not break parent class behavior.

**Interface Segregation Principle (ISP)**

- Clients should not depend on interfaces they don’t use.

- Example:
  
  ```
  interface HugeInterface { void f1(); ... void f50(); } 
  interface ParentInterface { void baseFunc(); } 
  interface Child1 extends ParentInterface { void func1(); } 
  interface Child2 extends ParentInterface { void func2(); }`
  ```
  
  → Split large interfaces into smaller, specific ones.

**Dependency Inversion Principle (DIP)**

- High-level modules should not depend on low-level modules; both depend on abstractions

- Example:
  
  ```
  class Car { void drive() {} }
  class B { 
      private final Car car;
      // Constructor injection 
      B(Car car) { this.car = car; } 
  }
  ```

## Goal: Maintainability, Reusability, Extensibility



### 3. Composition vs Inheritance

- Composition = **has-a** relationship

- More flexible than inheritance; avoids tight coupling

- Often preferred over inheritance

- Example:

```
class Engine {} 
class Car { private Engine engine;} // Car has an Engine
```

### 4. Overloading vs Overriding

| Feature    | Overloading                            | Overriding                               |
| ---------- | -------------------------------------- | ---------------------------------------- |
| Definition | Same method name, different parameters | Same signature, different implementation |
| Binding    | Compile-time                           | Runtime                                  |
| Purpose    | Convenience                            | Polymorphism                             |

### 5. Abstract Class vs Interface

| Topic       | Abstract Class                       | Interface                           |
| ----------- | ------------------------------------ | ----------------------------------- |
| Inheritance | One allowed                          | Multiple allowed                    |
| Members     | fields + concrete methods allowed    | abstract + default + static methods |
| Use case    | Shared base + partial implementation | Behavior contract                   |
