#  Association

 Definition

* Association is a general relationship where one class uses another class.
* Objects are independent
* No ownership
* Lifetime is separate
* Both objects exist independently
* Association represents a “uses-a” relationship with no ownership.


One class knows about the other

 Example (Teacher–Student)
 
      class Student {
      public:
          string name;
      };
      
      class Teacher {
      public:
          void teach(Student s) {
              cout << "Teaching " << s.name;
          }
      };




#  Aggregation (HAS-A relationship – Weak ownership)

Definition

* Aggregation is a special form of association where one object has another object, but does not own its lifetime.
* Objects can exist independently
* Uses pointers or references
* Parent does NOT destroy child
* Aggregation models a HAS-A relationship with shared ownership.


 Example (Department–Teacher)
 
    class Teacher {
    public:
        string name;
    };
    
    class Department {
        Teacher* t;   // pointer → weak ownership
    public:
        Department(Teacher* teacher) {
            t = teacher;
        }
    };

# Composition (Strong HAS-A relationship)
 Definition

* Composition is a strong ownership relationship where the contained object’s lifetime depends on the container.
* Child cannot exist without parent
* Created & destroyed together
* No pointers required
* Composition represents a strong HAS-A relationship where object lifetimes are tightly coupled.

 Example (Car–Engine)
 
    class Engine {
    public:
        Engine() {
            cout << "Engine created\n";
        }
    };
    
    class Car {
        Engine e;   // direct object → strong ownership
    };


Feature	                 Association	                Aggregation	                 Composition

Relationship	            uses-a	                       iss-a	                       has-a

Ownership	                 No	                           Weak	                        Strong

Lifetime dependency	       No	                             No	                          Yes

Pointer                   usedOptional	                  Yes                          	No

Example               	Teacher–Student              	Dept–Teacher	                  Car–Engine

# Friend Functions & Friend Classes

### Friend Function

Definition

* A friend function can access private and protected members of a class.
* Not a class member
* Breaks encapsulation (used carefully)
* Friend functions are used when external functions need access to private data.


Example

    class Box {
    private:
        int width;
    public:
        Box() { width = 10; }
        friend void showWidth(Box b);
    };
    
    void showWidth(Box b) {
        cout << b.width;
    }


### Friend Class
Example

      class A {
      private:
          int x;
          friend class B;
      };
      
      class B {
      public:
          void show(A a) {
              cout << a.x;
          }
      };

* All member functions of friend class can access private members
* Friendship is not inherited and not transitive

  
