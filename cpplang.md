* Organize related data into classes and structs.
* Use classes for data members that have invariants. Use structs when data members operate independently of one another.
* Separate the interface from its implementation.
* Add member functions only if they need direct access to member variables. Otherwise, separate them into helper functions.
* Helpers should be in the same namespace as the classes they support.


Warning. This is not a beginners guide. This is mostly documentation of syntax and high-level concepts which you will encounter in C++.

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
X 
```
