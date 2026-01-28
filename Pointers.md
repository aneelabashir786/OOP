## What is Pointer?

A pointer is a variable that stores the memory address of another variable.

&x → address of variable x

*p → value stored at the address (dereferencing)

    int x = 10;
    int* p = &x;  // p stores address of x
    cout << *p;  // Output: 10


Q: Difference between pointer and reference?

A: * Pointer can change what it points to; reference cannot.
   * Pointer can be NULL; reference cannot.


    int* p;    // pointer to int
    int x = 5;
    int* p = &x;
    cout << *p  // 5
    *p = 20 
    cout << x // 20

Dereferencing allows us to access or modify the value stored in memory.

### Pointer Arithmetic:

  Dereferencing allows us to access or modify the value stored in memory.
  Operations allowed on pointers
  
 *  p++ → moves to next memory location (depends on data type)
  
 *  p-- → moves to previous memory location
  
 *  p + n / p - n → moves n elements forward/backward


### Pass by Pointer

Allows function to modify original variable

    void update(int* x) {
        *x = 50;
    }
    
    int main() {
        int a = 10;
        update(&a);
        cout << a;   // Output: 50
    }
    
### Returning Pointers

Functions can return pointer (e.g., dynamic memory allocation)

    int* getArray(int n) {
        int* arr = new int[n];
        return arr;
    }



#### What is Dynamic Memory Allocation?

Dynamic memory allocation is allocating memory at runtime instead of compile time.
This allows programs to handle variable-sized data efficiently.

In C++ we use:

* new → allocate memory
* delete → free memory ( to avoid memory leak) 

      int* p = new int;  // allocate memory for one int
      *p = 10;           // store value
      cout << *p;        // 10
      delete p;          // free memory


#### Shallow Copy

Copies only pointer addresses, not actual data

Both objects point to the same memory → risky

      int* arr1 = new int[5]{1,2,3,4,5};
      int* arr2 = arr1;  // shallow copy
      arr2[0] = 10;
      cout << arr1[0];   // Output: 10 (both changed!)

#### Deep Copy

Copies actual data into a new memory

Objects independent

      int* arr1 = new int[5]{1,2,3,4,5};
      int* arr2 = new int[5];
      for(int i=0; i<5; i++)
          arr2[i] = arr1[i];  // deep copy
      arr2[0] = 10;
      cout << arr1[0];   // Output: 1 (original unchanged)

Deep copy avoids unexpected side-effects when multiple pointers reference the same memory.

#### Explain dangling pointer

Answer: Pointer pointing to freed memory. Avoid by setting pointer to nullptr after delete.

#### Difference between new and malloc()?

Answer: new calls constructor, malloc() doesn’t. new returns correct type, malloc() returns void*.
  

