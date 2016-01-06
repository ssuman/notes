## Java 8 in Action

#### Chapter 2

Use of strategy pattern is simplified in java 8.
Different ways of selecting numbers.

> numbers.stream().filter(i -> i%2 ==0);

> numbers.stream().filter(i -> i > 1);


> Collections.sort(numbers, (a, b) -> a.compareTo(b));


#### Chapter 3

* Lambdas in a nutshell

Lambda expression is an anonymous function: it doesn't have a name, but has parameters, a body , a return type and also a list of exceptions that can be thrown.

Examples:

	() -> {}  
	() -> "Raoul" 
	() -> {return "Mario";} 
	(Integer i) -> return "Alan" + i; // Invalid lamba.
	(String s) -> {"Iron Man"; }   // Invalid lambda.;

* Where and how to use Lambdas ?

Lambdas can be used in the context of a functional interface. Functional interface is an interface that specifies exactly one abstract method.

	public interface Comparator<T> {
		int compare(T o1, T o2);   // only abstract method.
	}
An interface is still a functional interface if it has many default methods as long as it specifies only one abstract method.

Common Functional interfaces listed below

|Functional Interface | Function descriptor | primitive specialization |
|---------------------|---------------------|--------------------------|
| Predicate<T>        | T -> boolean        | IntPredicate             |
| Consumer<T>         | T -> void           | IntConsumer              |
| Function<T, R>      | T -> R              | IntFunction              |
| Supplier<T>         | () -> T             | BooleanSupplier          |
| UnaryOperator<T>    | T -> T              | IntUnaryOperator         |
