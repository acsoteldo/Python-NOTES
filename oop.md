### Object-Oriented Programming (OOP)

**What is OOP?**
- Object-Oriented Programming (OOP) is a programming paradigm that uses objects and classes to structure code and data.
- OOP is based on the concept of "objects," which represent real-world entities and contain both data (attributes) and behaviors (methods).

**Key Concepts:**

1. **Class:**
   - A blueprint or template for creating objects.
   - Defines the attributes (data) and methods (functions) that objects of the class will have.

2. **Object:**
   - An instance of a class.
   - Contains data (attributes) and can perform actions (methods).

3. **Encapsulation:**
   - The bundling of data (attributes) and methods that operate on that data into a single unit (the object).
   - Provides data protection and access control through visibility modifiers (e.g., public, private, protected).

4. **Inheritance:**
   - A mechanism that allows one class to inherit the properties and methods of another class.
   - Promotes code reusability and the creation of hierarchies of classes.

5. **Polymorphism:**
   - The ability of different classes to be treated as instances of a common superclass.
   - Enables dynamic method invocation and method overloading.

**Benefits of OOP:**
- **Modularity:** Code is organized into reusable and manageable units (classes and objects).
- **Reusability:** Classes and objects can be reused in different parts of the program.
- **Maintainability:** Changes and updates are easier to implement due to encapsulation and abstraction.
- **Flexibility:** OOP allows for efficient adaptation to changing requirements.
- **Improved Collaboration:** Multiple developers can work on different classes without interference.

**Basic OOP Terminology:**

- **Attribute/Field/Property:** Data associated with an object or class.
- **Method/Function:** A function defined within a class that performs actions on data.
- **Constructor:** A special method used to initialize object attributes.
- **Instance:** A specific object created from a class.
- **Superclass/Base Class:** The class from which another class (subclass) inherits.
- **Subclass/Derived Class:** A class that inherits properties and methods from another class.
- **Abstraction:** Representing essential features of an object while hiding unnecessary details.
- **UML (Unified Modeling Language):** A visual representation of classes, objects, relationships, and methods.

**Example in Python:**

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def start_engine(self):
        return f"The {self.make} {self.model}'s engine is running."

my_car = Car("Toyota", "Camry")
print(my_car.start_engine())
```

In this example, `Car` is a class, `my_car` is an object, and `start_engine` is a method.

---

This introductory cheat sheet covers the fundamental concepts and terminology of Object-Oriented Programming (OOP). It's a foundation for understanding how OOP organizes code and data in a structured and reusable manner.
