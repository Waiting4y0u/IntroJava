Conditionals (if)
===

Many times, in life and programming, we need to act differently depending on certain conditions. In Java we do this with an if statement. 

# Syntax
The syntax is simple:
```java
if (condition) {
    ...
} else {
    ...
}
```

And a real example (inside a function):
```java
public static String booleanToYesNo(boolean b)
{
    if( b ) {
        return "Yes";
    } else {
        return "No";
    }
}
```

A few highlights about the syntax:
+ The parenthesis around the condition are required 
+ the braces are not strictly required; if you don't put braces then only the first statement is considered to be inside the if; it is a very good idea to always put braces, so feel free to use it as if they were required :)
+ the `else` clause is not required; you can have an `if` with no `else`, and in that case nothing gets done if the condition is not met.
+ *indentation* (starting some lines deeper than others) is important, although not required by the language. It is impportant to use a *consistent* indentation scheme, although it usually doesn't matter which particular one you use. 
    + Your IDE can automatically indent code (source/format in Eclipse).
    + Use indentation to show structure; basically, every { leads to a deeper level of indentation
    + tabs vs spaces is a thing (yeah, is what we geeks do)
    + Whether the { goes on a new line is also subject to debate :(
    + be consistent !
## another example

Let us define the abs function, which returns the absolute value of an int (the absolute value is always positive).

```java
	public static int abs(int number)
	{
		if(number<0) {
			return -number;
		} else {
			return number;
		}
	}
```
    
# nested if statements

Inside the braces for an if/else, we can put any statements, including another if statement. We call an if inside another if a *nested* if statement. As far as Java is concerned, we can nest at any level, although if our conditions are too complicated, chances are we're approaching the problem wrong.

As an example, let us defne the `sign` function, which takes a number and returns -1 if the number is negative, 1 if positive and 0 if 0.

```java
	public static int sign(int number)
	{
		if( number<0 ) {
			return -1;
		} else {
			if ( number>0 ) {
				return 1;
			} else {
				return 0;
			}
		}
	}
```

# chained if statements

Many times we have more than two mutually exclusive possibilities; in that case, we normally write them as a chained if statement (tecnically, this are nested if statements, with the nesting happening in the else part, but we format them with all options at the same level, which makes more sense).

For example, we could write the sign function as follows:
```java
	public static int sign(int number)
	{
		if( number<0 ) {
			return -1;
		} else if ( number>0 ) {
			return 1;
		} else {
			return 0;
		}
	}
```

# Ternary operator

Java has an operator that works similar to an if statement, but it yields a value (as it is an operator). It syntax is like this:
```java
condition ? valueForTrue : valueForFalse
```
For example, we could write the abs function as follows:
```java
	public static int abs(int number)
	{
		return number<0 ? -number : number;
	}
```
# Exercises