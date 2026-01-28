## Structures:

A structure is a user-defined data type that groups variables of different types under a single name.
Structures allow us to represent real-world entities with multiple attributes.

* Unlike C, C++ structures support methods, making them almost like classes.

      struct Student {
        int id;
        float cgpa;
        void display() {
            cout << "ID: " << id << ", CGPA: " << cgpa << endl;
        }
      };
      Student s1 ;
      s1.id = 123
      s1.cgpa = 3.5
      s1.display()

## Array of Structures

Used to store multiple records of the same type.

    Student s[50];   // array of 50 students
    s[0].id = 101;
    strcpy(s[0].name, "Aneela");


Array of structures is widely used in database-like applications to store multiple records efficiently.

## Structures and Pointers

You can have pointers to structures

    Student s1;
    Student* ptr = &s1;
    
    ptr->id = 102;       // access using arrow operator
    ptr->cgpa = 3.9;


You can also create dynamic structures

    Student* s = new Student;  
    s->id = 103;
    delete s;  // free memory

Pointers with structures are common in dynamic data storage, like linked lists or trees.




