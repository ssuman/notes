## Effective Java Notes -
### Item 1 - Consider Static factory methods instead of constructors.
1. Advantages of static factory methods are:
	* Static factory methods have names unlike constructors.
	* Static factory methods are not required to create a new Object each time they are invoked.
	* Static factory methods can return an object of any subtype.
	* Static factory methods can reduce verbosity of creating parameterized type instances.
2. Disadvantage of static factory methods are:
	* Providing only static factory methods without public or protected constructors cannot be subclassed.
	* Not readily distinguishable from other static methods.

### Item 5 - Avoid creating unnecessary objects
1. Reuse of a single object instead of creating a new object each time is both faster and stylish.
2. Static factory methods often avoid creating unnecessary objects. 
3. Boolean.valueOf(String) is preferable to constructor Boolean(String).
4. Mutable objects can also be reused if we know the object won't be modified.
5. Static initialization blocks can be used to initialize the mutable object once.
6. Autoboxing also creates unnecessary objects. Prefer primitives to boxed primitives.

### Item 7 - Avoid finalizers
1. Java finalizers not analogous to c++ destructors.
2. Java Finalizers may or may not be invoked.
3. Do not put critical code in finalizers instead put them in try..finally{}
4. Finalizers have performance problems.

### Item 15 - Minimize mutability
1. Five rules to follow to create a immutable class.
	* Don't provide any "setter" methods.
	* Ensure that the class can't be extended.
	* Make all fields final and private.
	* When multable member is present, ensure clients of the class cannot obtain references to these objects. Provide defensive copies.
2. Immutable objects are inherently thread safe. They require no synchronization.
3. Clone or copy constructor should not be provided on an immutable class.
3. Immutable classes create many objects hence can cause performance problems. Can be solved by providing a mutable companion.

### Item 16 - Favor Composition over inheritance
1. It is safe to use inheritance within a package, where the subclass and superclass are under the control of the same programmer.
2. Inheriting across package boudaries is dangerous.
3. Inheritance violates encapsulation. The superclass implementation may change from release to release. This might break the subclass.
4. Problem can be solved by using composition and forwarding methods. 