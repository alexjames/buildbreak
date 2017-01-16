### The C language
C is a fairly modest language. It has no strings, sets, lists or arrays; no heap or garbage collection;
no input/output or file access methods; no multi-programmins, synchronization or parallel programming 
methods. All this keeps C free from bloat and allows a user to quickly master and use most of the language.

"C relies on the philosophy that programmers know what they are doing; it only requires that they state
their intentions explicitly." - KnR


### simple C program
```
#include <stdio.h>
main()
{
  printf("hello, world\n");
}
```

The C standard says that #include "" or #include <> both search for headers in an implementation defined manner.
In GCC, #include <stdio.h> searches for stdio.h in the standard list of system directories. #include "stdio.h"
will first attempt to search for stdio in the same directory as the source file, before defaulting to the
standard list.

Program execution starts at the main function. Every executable program has to have this function.

### printf format specifiers

| Format        | Action        |
| ------------- |:-------------:| 
| %c     | character | 
| %f     | float or double | 
| %d     | integer | 
| %p     | pointer | 
| %u     | unsigned | 
| %x     | hexadecimal | 
| %6d     | print integer at least 6 charactesr wide | 
| %6.2f     | print float 6 characters wide, 2 characters after decimal | 

### variables and scope

declaration - specifies the name and type of an object

definition - causes storage to be allocated to an object

Local variables declared within a function are only visible within the scope of that
function. These are known as automatic variables. These are variables put on the stack.

The `extern` keyword specifies that a particular variable has been defined outside the current
scope. It is common practice to place all definitions of external variables at the beginning
of the source file. This way, the extern declarations can be omitted. Extern can only be used
in declarations.

```
The following code snippet would fail to compile if you skip the extern declaration.
int main()
{
    extern int a;
    a = 5;
    return 0;
}

int a;
```

Variable names can contain letters, numbers and "_". The variable name must begin with a letter or "_",
though we avoid starting them with "_" since library routines tend to use these.


| Declaration | 32-bit | 64-bit |
| ----------- |:------:|:------:|  
| char | 1 | 1 |  
| short int | 2 | 2 |  
| int | 4 | 4 |  
| long int | 4 | 8 |  
| long long int | 8 | 8 |  
| char * | 4 | 8 |  
| float | 4 | 4 |  
| double | 8 | 8 | 

Examples of definitions:
```
    int i = 6;
    char ch = 'd';
    float f =  99.93e-2f;    // 99.93 * 10 ^ -2, suffix of f indicates a single-precision (float)
    double d = 3.5;          // no suffix for doubles
```

### functions

In C, all function arguments are passed by value - which means the function is given the values of its arguments
in temporary variables rather than the originals.

