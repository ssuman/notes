## Java 8 in Action

#### Chapter 2

Use of strategy pattern is simplified in java 8.
Different ways of selecting numbers.

> numbers.stream().filter(i -> i%2 ==0);

> numbers.stream().filter(i -> i > 1);


> Collections.sort(numbers, (a, b) -> a.compareTo(b));


#### Chapter 3

Lambda expression is an anonymous function: it doesn't have a name, but has parameters, a body , a return type and also a list of exceptions that can be thrown.

Examples:

> () -> {}  
<!>
> () -> "Raoul" 
<!>
> () -> {return "Mario";} 
<!>
> (Integer i) -> return "Alan" + i; // Invalid lamba.; 
> (String s) -> {"Iron Man"; }   // Invalid lambda.;