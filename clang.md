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

