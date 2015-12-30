## Effective Java Notes -

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
2. Immutable classes create many objects hence can cause performance problems. 