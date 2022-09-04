## Monday 29/08/22

### Readme - OOP

**What is Object Oriented Programming?**

Object-oriented programming, or OOP, is an approach to problem solving 
where all computations are carried out using objects. An object is a 
component of a program that knows how to perform certain actions and how 
to interact with other elements of the program. Objects are the basic units 
of object-oriented programming. A simple example of an object would be a 
person. Logically, you would expect a person to have a name. This would be 
considered a property of the person. You could also expect a person to be able
to do something, such as walking or driving. This would be considered a method
of the person.

**OOP Glosary**

- **Abstraction**
  
 Objects only reveal internal mechanisms that are relevant for the use of other objects, hiding any unnecessary implementation code. The derived class can have its functionality extended. This concept can help developers more easily make additional changes or additions over time.

- **Inheritance**

Classes can reuse code from other classes. Relationships and subclasses between objects can be assigned, enabling developers to reuse common logic while still maintaining a unique hierarchy. This property of OOP forces a more thorough data analysis, reduces development time and ensures a higher level of accuracy.

- **Polymorphism**

Objects are designed to share behaviors and they can take on more than one form. The program will determine which meaning or usage is necessary for each execution of that object from a parent class, reducing the need to duplicate code. A child class is then created, which extends the functionality of the parent class. Polymorphism allows different types of objects to pass through the same interface.

- **Encapsulation**

This principle states that all important information is contained inside an object and only select information is exposed. The implementation and state of each object are privately held inside a defined class. Other objects do not have access to this class or the authority to make changes. They are only able to call a list of public functions or methods. This characteristic of data hiding provides greater program security and avoids unintended data corruption.

- **Class**

are user-defined data types that act as the blueprint for individual objects, attributes and methods.

- **Object**

are instances of a class created with specifically defined data. Objects can correspond to real-world objects or an abstract entity. When class is defined initially, the description is the only object that is defined.

- **Instance**

is a specific realization of any object.
An object may be varied in a number of ways, each realized variation of that object is an instance.
The creation of a realized instance is called instantiation.

- **Interface**

An interface is a programming structure/syntax that allows the computer to enforce certain properties on an object (class). For example, say we have a car class and a scooter class and a truck class. Each of these three classes should have a start_engine() action.

- **Access Modifiers**

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. Access modifiers are a specific part of programming language syntax used to facilitate the encapsulation of components.

- **Constructors**
A constructor is a special method of a class or structure in object-oriented programming that initializes a newly created object of that type. Whenever an object is created, the constructor is called automatically.

### Example of OOP in Typescript

Here we have a simple class made in Typescript:

```typescript
class Person {                        // Class declaration
  _greeting: string;                   // Properties
 
  constructor(greeting: string) {      // Constructor
    this.greeting = greeting;
  }
  
  get greeting(){                      // Accessors
  return this._greeting;
  }
  set greeting(greeting){
  this._greeting = greeting;
  }
 
  greet() {                           // Methods
    return "Hello, " + this.greeting;
  }
}
 
let greeter = new Greeter("world");   // Class Instantiaton
```


Here we declare a new Class named `Person`, 
