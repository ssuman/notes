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

An Interface intended as Functional interface can be annotated with @FunctionalInterface ! It isn't mandatory but is a good practice.

Predicate  -  Can be used when we have to represent a boolean lambda expression.

#### Chapter 4 - Streams

* Traversable Only Once

	Stream<String> s = title.stream();
	a.forEach(System.out::println);
	a.forEach(System.out::println);
	// Throws java.lang.IllegalStateExceptions: stream has already been operated upon.

* Two types of stream operations intermediate and terminal.
* Intermediate operations return another stream but doesn't perform processing. They are lazily evaluated.
* Due to lazy evaluation, optimizations such as short-circuiting and loop fusion is possible.
* Terminal operations produce a result from a stream pipeline.

Intermediate Operations:

| Operation | Argument Operation | Function Descriptor |
|-----------|--------------------|---------------------|
| filter    | Predicate          |  T -> boolean       |
| map       | Function<T, R>     |  T -> R             |
| limit     |                    |                     |
| sorted    |  Comparator        |  (T, T) -> int      |
| distinct  |                    |                     |

Terminal Operations:

| Operation |  Purpose |
|-----------|----------|
| forEach   | Consumes each element from a stream and applies a lambda. Return void |
| count     | Returns number of items in a stream. Returns long |
| collect   | Reduce stream to list, map or int                 |


