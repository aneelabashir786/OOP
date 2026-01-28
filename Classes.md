# Class 

Blueprint of an object.

# Object

Instance of a class.

    class Car {
    public:
        int speed;
        void drive() {
            cout << "Car is moving";
        }
    };
    
    Car c1;   // object

 # Member Functions
 
1.  Accessor (Getter)
   
   * Reads data

    int getSpeed() {
        return speed;
    }

2.  Mutator (Setter)
   
    * Modifies data

          void setSpeed(int s) {
              speed = s;
          }

4. Utility Functions
   
    * Support logic (calculate, validate, etc.)

Interview line:

Accessors and mutators support encapsulation.



## What is a static data member?

A static data member belongs to the class, not to individual objects.
Static data members are used to maintain shared information among all objects.

* Only one copy shared by all objects
* Created once, exists throughout program

      class Student {
      public:
          static int count;
          Student() {
              count++;
          }
      };
      
      int Student::count = 0;   // definition outside class
  
      Student s1, s2;
      cout << Student::count;  // Output: 2

 # What is a static member function?

* Belongs to the class
* Can access only static members
* Called using class name
* Static member functions are useful for operations that do not depend on object-specific data.

➤ Example:

      class Student {
      public:
          static int count;
          static int getCount() {
              return count;
          }
      };
      
      cout << Student::getCount();

# What is a const data member?

* Value cannot be changed
* Must be initialized using constructor initializer list
* Const members ensure data integrity by preventing modification.

➤ Example:

    class Student {
        const int id;
    public:
        Student(int i) : id(i) {}  // initializer list
    };

This is NOT allowed:

      id = i;   // error

# What is a const member function?

* Cannot modify object data
* Used for read-only operations
* Const member functions guarantee that object state remains unchanged.

➤ Example:

      class Student {
          int marks;
      public:
          int getMarks() const {
              return marks;
          }
      };

# What is this pointer?

* this is an implicit pointer that holds the address of current object 
* Used to resolve naming conflicts

# Constructor 

A constructor is a special member function:

* Same name as class
* Called automatically when an object is created
* Used to initialize data member
* A constructor initializes an object and ensures it starts in a valid state.

➤ Example:

      class Student {
          int id;
      public:
          Student(int i) {
              id = i;
          }
      };

# Destructor 

* Called automatically when an object is destroyed
* Used to free resources
* Same name as class with ~
* Destructors prevent memory leaks by releasing allocated resources.


➤ Example:

    class Student {
    public:
        ~Student() {
            cout << "Object destroyed";
        }
    };

# Data Abstraction

* Showing only essential features and hiding implementation details.
* Data abstraction reduces complexity and improves maintainability.


➤ Achieved using:

* Classes
* Access specifiers (private, public)

# Abstract Data Type (ADT)

An ADT defines:

* What operations are allowed
* Not how they are implemented
* ADTs separate interface from implementation.

Stack ADT → push, pop, peek


# Copy Constructor

* A constructor that creates an object using another object of the same class.
* Copy constructor ensures proper copying of objects.

      Student(Student &obj) {
          id = obj.id;
      }


#  Overloaded Constructors

Multiple constructors with different parameters.
Overloading constructors provides flexibility in object creation.

    class Student {
    public:
        Student() {}
        Student(int i) { id = i; }
    };





