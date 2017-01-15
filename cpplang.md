* Organize related data into classes and structs.
* Use classes for data members that have invariants. Use structs when data members operate independently of one another.
* Separate the interface from its implementation.
* Add member functions only if they need direct access to member variables. Otherwise, separate them into helper functions.
* Helpers should be in the same namespace as the classes they support.


Warning. This is not a beginners guide. This is mostly documentation of syntax, high-level concepts and best-practices which you will encounter in C++.

# Sample C++ program

```
#include<iostream>
using namespace std;

int main()
{
	cout << "hurray" << endl;
	return 0;
}
```
This will compile and work without any issues. No problems here except for the `using namespace std` part.This will
include everything in the std namespace to the global namespace. This can cause naming conflicts.

Here are alternatives -
Declare it within the scope of a function:
```
void f()
{
  using namespace std;
  cout << "lol" << endl;
}
```
OR only import the symbols you need into the global namespace.
```
using std::cout;
using std::endl;

void f()
{
  cout << "lol" << endl;
}
```

Classes in C++ are user-defined types that consists of data members (variables) and member functions. Public members are visible to the outside word. Private members are invisible and only accessible inside the class. A class is a namespace that contains its members.

```
class X
{
  private:
    int you_cant_see_me;
    char you_cant_see_me_either;
    int do_class_related_stuff();
    
  public:
    int you_can_access_this;
    int make_this_object_do_something();
};
```
This is how you create an object of type X.

```
X x
x.you_can_access_this = 4;           // works
x.make_this_object_do_something();   // works
x.you_cant_see_me = 6;               // FAILS! Accessing a private data memeber
```
This is how you define member functions -

```
int X::make_this_object_do_something()
{
	you_cant_see_me = 6;         // okay to access private data memeber
}
```

