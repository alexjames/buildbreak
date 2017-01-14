* Organize related data into classes and structs.
* Use classes for data members that have invariants. Use structs when data members operate independently of one another.
* Separate the interface from its implementation.
* Add member functions only if they need direct access to member variables. Otherwise, separate them into helper functions.
* Helpers should be in the same namespace as the classes they support.
