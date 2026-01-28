## What is OOP?

Object-Oriented Programming (OOP) is a programming paradigm that organizes code using objects which contain data (attributes) and behavior (methods).
It helps in writing reusable, scalable, and maintainable code.


##  Procedural Programming

* Focus on functions
* Data is shared
* Less secure

##  Object-Oriented Programming

* Focus on objects
* Data encapsulated
* More scalable

Interview line:

OOP is better suited for large, complex systems.


## Object-Oriented Design (OOD)

* Planning stage
* Identifying classes & relationships

## Object-Oriented Programming (OOP)

* Implementation stage
* Writing code using classes & objects

Interview line:

OOD defines the structure, OOP implements it.

## 4 pillors of OOP

1. Encapsulation

Definition:
Encapsulation means binding data and methods together and restricting direct access to data.
Encapsulation improves data security and code maintainability.

How:
Using access specifiers like private, protected, and public.

2. Abstraction

Definition:
Abstraction means hiding implementation details and showing only essential features.
Abstraction focuses on what an object does, not how it does it.

How:
Using abstract classes or interfaces.

An abstract class is a class that cannot be instantiated (object cannot be created) and is used only as a base class. ( can be inherited) 

It may contain:

* abstract (pure virtual) functions → no implementation
* normal functions → with implementation

       virtual void draw() = 0;

3. Inheritance

Definition:
Inheritance allows a class to reuse properties and behavior of another class.
Inheritance promotes code reusability and hierarchical relationships.

 3.1 Multiple Inheritance
 
A class inherits from more than one base class.
Ambiguity occurs in multiple inheritance when base classes contain functions with the same name.

              class A {
              public:
                  void show() { cout << "A"; }
              };
              
              class B {
              public:
                  void show() { cout << "B"; }
              };
              
              class C : public A, public B {};

-> Ambiguity Error (Very Important )
*  Problem:
  
              C obj;
              obj.show();  // ERROR: ambiguous

* Solution:

-> Use scope resolution operator

              obj.A::show();
              obj.B::show();


Polymorphism

Definition:
Polymorphism allows the same function name to behave differently.
Polymorphism makes the system flexible and extensible.

Types:

Compile-time  / Static Polymorphism (function overloading)

Polymorphism that is resolved at compile time.

➤ How is it achieved?

* Function Overloading
  
  Function overloading allows you to define multiple functions with the same name but different
  parameter lists (number, type, or order of parameters) within the same scope
  
      class Math {
      public:
          int add(int a, int b) {
              return a + b;
          }
          double add(double a, double b) {
              return a + b;
          }
      };


* Operator Overloading
  
  Operator overloading lets you redefine the behavior of standard operators (like +, -, *) for user-defined types
  (classes/objects) in object-oriented programming, allowing them to perform specific actions on those objects

      class Point {
        public:
            int x, y;
            Point operator+(Point p) {
                Point temp;
                temp.x = x + p.x;
                temp.y = y + p.y;
                return temp;
            }
        };
        

Run-time / Dynamic Polymorphism (method overriding)


* Function Overriding :
  
Function overriding is an Object-Oriented Programming (OOP) concept where a derived class provides a specific implementation for a function that is already defined in its base class, using the same name, return type, and parameters, enabling runtime polymorphism and allowing different behaviors for the same function call across classes.

      class Shape {
      public:
          virtual void draw() {
              cout << "Drawing shape";
          }
      };
      
      class Circle : public Shape {
      public:
          void draw() {
              cout << "Drawing circle";
          }
      };

      Shape* s;
      Circle c;
      s = &c;
      s->draw();   // Output: Drawing circle


# Diomand Problem

The diamond problem occurs in multiple inheritance when a class inherits from two classes having a common base class, 
causing ambiguity and duplication. It is solved using virtual inheritance.

* If multiple inheritance happens later, share the base class.
* It ensures only one instance of a base class exists within an inheritance hierarchy

solution: 

              class A {
              public:
                  int x;
              };
              
              class B : virtual public A { };
              
              class C : virtual public A { };
              
              class D : public B, public C { };
       

