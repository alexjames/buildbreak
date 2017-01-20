#include<memory>

Smart pointers are classes that act like pointers eg by overloading * and -> opperators. 
They are mostly used for safe dynamic memory management.

std::unique_ptr acts as a single unique pointer to a resource; this reference cannot be copied.
```
unique_ptr <T> myPtr (new T);

unique_ptr <T> otherPtr = myPtr; // compilation error
```
The object is destroyed when the pointer goes out of scope.

std::shared_ptr allow multiple pointers to point to the same object, the object is destroyed when the 
pointer goes out of scope.
