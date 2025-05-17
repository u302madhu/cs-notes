# Java Programming

**Course:** [Java Programming by University of Helsinki](https://java-programming.mooc.fi/)

## Part 1
### Getting started with programming
Modern programming is practically always done in an **integrated development environment** (IDE). An IDE is a software for building applications that combine common developer tools into a single **graphical user interface** (GUI).

Programming is designing and implementing software. Programs are typically implemented in a programming language meant to be written and read by humans.

Programming languages have many commands built-in that a programmer uses when developing software. This makes programming easier as you don't need to implement everything from scratch. Indeed, a large part of programming is making use of available functions and tools in solving problems.

The code you write is called source code. Source code consists of statements and expressions, which are read line by line from top to bottom, and from left to right.

---

### Printing
The print command, built-in into Java helps you to print the text given to it.
```java
System.out.println("Hello, World!");
```

In Java, our programs have to include some boilerplate code to function. This boilerplate, for example tells the computer what your program is called. The name of the program has to correspond to the name of the file that contains the source code.

Printing.java
```java
public class Printing {
	public static void main(String[] args) {
		System.out.println("Hello, World!");
	}
}
```

When a program is run, a lot is happening behind the scenes. When a program is run, the source code is first compiled into Java bytecode. This compilation process is done by Java's compiler, which itself is a program. Following that, the program gets executed by a Java interpreter that is able to read Java bytecode.
This compile process affects how and when errors occur. When a program is compiled before execution, the compiler can search for errors in it.
The programming environment compiles the program continuously, so it can report errors.

Programs are constructed command-by-command, where each command is placed on a new line. Commands are separated with a semicolon. We could, if we wanted to, write almost everything on a single line. However, that would be difficult to understand.

Source code can be commented to clarify it or add notes. The computer will ignore them when executing the program. There are two ways to do this.
- Single-line comments are marked with two slashes `//`. Everything following them on the same line is interpreted as a comment.
- Multi-line comments are marked with a slash and an asterisk `/*`, and closed with an asterisk followed by a slash `*/`. Everything between them is interpreted as a comment.
Code that has been written does not need to be deleted to try out something else, it can just be commented.

---

### Reading Input
Input refers to text written by the user read by the program. Input is always read as a string.

For reading input, we use the `Scanner` tool that comes with Java. The tool can be imported for use in a program by adding the command `import java.util.Scanner;` before the beginning of the main program's frame. The tool itself is created with `Scanner scanner = new Scanner(System.in);`.

Input.java
```java
// Introduce the scanner tool used for reading user input
import java.util.Scanner;

public class Input {
	public static void main(String[] args) {
		// Create a tool for reading user input and name it scanner
		Scanner scanner = new Scanner(System.in);
		
		System.out.println("Write a message: ");
		
		// Read the string written by the user, and assign it to program memory
		String message = scanner.nextLine();
		
		System.out.println(message);
	}
}
```

More precisely, input is read with the `scanner` tool's `nextLine()` method. The call `scanner.nextLine()` is left waiting for the user to write something. When user writes something and presses enter, the provided string is assigned to a **string variable**. The program is then able to reference the variable later on.

In programming, we refer to "strings" rather than "text". The term "string" is shorthand for "string of characters" which describes how the computer sees text on a more fundamental level: a sequence of individual characters.

Variables are named containers that contain information of some specified type and have a name.
A variable is declared in a program by stating the type of the variable and its name. Typically a variable is also assigned a value during its declaration. You can assign a value by following the declaration with an equals sign followed by the value and a semicolon.

```java
String message = "Hello, World!";
```

A string enclosed in a programming language's quotation marks is called a "string literal", i.e., a string with a specified value.

A string can be formed from multiple strings using the `+` operator. Using this operator to join multiple strings is called **string concatenation**.

When the program's execution comes to a statement that attempts to read input from the user (the command `scanner.nextLine()`), the execution stops and waits. The execution continues only after the user has written some input and pressed enter.

---

### Variables
A variable can be thought of as a container in which information of a given type can be stored. Examples of these different types include text (`String`), whole numbers (`int`), floating-point numbers (`double`), and whether something is true or false (`boolean`). A value is assigned to a variable using the equals sign (`=`).

A variable's value can be joined to a string using the `+` sign.

Variable names are unique - no two variables have the same name. A variable is created the first time its declared.
The variable type is stated when the variable is first declared. When a new value is assigned to the variable, the type is no longer declared.

A variable exists from the moment of its declaration, and its initial value is preserved until another value is assigned to it. You can change a variable's value using a statement the comprises the variable name, an equals sign, and the new value to be assigned. The variable type is only stated during the initial variable declaration.

```java
int value = 10;
System.out.println(value);

value = 4;
System.out.println(value);
```

Whenever a value is assigned to a variable, a check is run to see whether a container with the given name already exists. If one does, a new value is copied in place of the old value, and the old value disappears. If a container of the variable name is not found, the program execution ends in an error message, or it fails to run.
A variable can hold only one value at a time.

Once a variable's type has been declared, it can no longer be changed. For example, a boolean value cannot be assigned to a variable of the integer type, nor can an integer be assigned to a variable of the boolean type.
However exceptions do exist: an integer can be assigned to a variable of the double type, since Java knows how to convert an integer to a double during assignment.
A floating-point value cannot, however, be assigned to an integer variable. This is to prevent developers from making errors that lead to a loss of information.

```java
double doubleValue = 0.42;
doubleValue = 1; // Works

int integerValue = 10;
integerValue = 4.2 // Does not work
```

Variables express the program and the problem to be solved.
Variable naming is limited by certain constraints. Variable names cannot contain certain special symbols. Spaces are also not allowed, since they are used to separate parts of commands. Instead of spaces, the convention in Java is to use a style known as camelCase. The first letter of each word is capitalised, except the first letter of the entire compound word, which should be lower-cased. Numbers can be used within a variable name as long as the name does not begin with a number. A variable's name cannot already be in use. These names include, for instance, variables previously defined in the program and commands provided by Java.

A variable's type is specified when it is initially declared. A variable's type determines the types of values that can be assigned to it.

| Type                             | Example                 | Accepted Values                                                                                                                                                                                                                                                                             |
| -------------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `int` (Whole number)             | `int value = 4;`        | An integer can contain whole numbers whose values lie between -2147483648 and 2147483647.                                                                                                                                                                                                   |
| `double` (Floating-point number) | `double value = 4.2;`   | Floating-point numbers contain decimal numbers, with the greatest possible value being approximately 2<sup>1023</sup>. When a decimal number is represented with a floating-point number, the value can be inaccurate as floating-points are incapable of representing all decimal numbers. |
| `String` (Text)                  | `String text = "Hi";`   | A string contains text. Strings are enclosed in quotation marks.                                                                                                                                                                                                                            |
| `boolean` (True or False values) | `boolean right = true;` | A boolean contains either the value `true` or `false`.                                                                                                                                                                                                                                      |

The user's input is always read as a string. Other input types, such as integers, doubles, and booleans are also read as text. However, they need to be converted to the target variable's type with the help of some tools provided by Java.
The `Integer.valueOf()` command converts a string to an integer. It takes the string to be converted as a parameter. When using a Scanner object, the reading of the value is usually inserted directly into the type conversion.
The `Double.valueOf()` command converts a string to a double.
The `Boolean.valueOf()` command converts a string to a boolean. When converting a string to a boolean, the string must be "true" if we want the boolean value to be true. The case is insensitive here. All other strings turn into the boolean false.

```java
String booleanValueAsString = "tRUe";
String doubleValueAsString = "42.42";
String integerValueAsString = "42";

boolean booleanValue = Boolean.valueOf(booleanValueAsString);
double doubleValue = Double.valueOf(doubleValueAsString)
int integerValue = Integer.valueOf(integerValueAsString);

System.out.println(booleanValue);
System.out.println(doubleValue);
System.out.println(integerValue);
```

---

### Calculating with numbers
The basic math operations in Java are addition `+`, subtractions `-`, multiplication `*`, and division `/`. The operations are performed from left to right with the parentheses taken into account. Expressions involving `*` and `/` are calculated before those involving `+` and `-`. Operations within parentheses are performed before those outside them.
The modulo operator `%` is used to check the divisibility of a number.

An *expression* is a combination of values that is turned into another value through a calculation or evaluation. A *statement* is a complete instruction that performs an action.

If one of the operands of the operation `+` is a string, the other operand will be changed into a string too during program execution.

The type of the variables that are part of the division determine the type of result achieved by executing the command.
If both the operands in the division are integers, the result will be an integer. If one of them is a floating-point number, the result is a floating-point number.
An integer can be converted into a floating-point number by placing a type-casting operation `(double)` before it.

```java
int first = 3;
int second = 2;
double third = 2.0;

System.out.println(first / second); // 1
System.out.println(first / third); // 1.5
System.out.println((double) first / second); // 1.5
```

---

### Conditional statements and conditional operation
To branch the execution of a program based on some variable, we need to use something known as **conditional statement**.

A conditional statement begins with the keyword `if` followed by parentheses. An expression is place inside the parentheses, which is evaluated when the conditional statement is reached. The result of the evaluation is a boolean value. The parentheses are followed by a block, which is defined inside opening - `{` and closing `}` curly brackets. The source code inside the block is executed if the expression inside the parentheses evaluates to *true*.
If an `else` branch has been specified for a conditional statement, the block defined by the else branch is run in the case that the condition of the conditional statement is false.
In case of multiple conditionals, we use the `else if`-command. It is like `if`, but with an additional condition.
The comparisons are executed top down. When execution reaches a conditional statement whose condition is true, its block is executed and the comparison stops.

```java
int number = 3;

if (number == 1) {
    System.out.println("The number is one");
} else if (number == 2) {
    System.out.println("The given number is two");
} else if (number == 3) {
    System.out.println("The number must be three!");
} else {
    System.out.println("Something else!");
}
```

If the expression evaluates to false, the execution moves on to the statement after the closing curly bracket of the current conditional statement.

A code block refers to a section enclosed by a pair of curly brackets. Blocks define a program's structure and its bounds. Code living inside a block is indented to make it more readable.

We cannot compare the equality of strings using two equals signs. This has to do with the internal workings of strings as well as how variable comparison is implemented in Java. In practice, the comparison is affected by how much information a variable can hold - strings can hold a limitless amount of characters, whereas integers, floating-point numbers, and boolean values always contain a single number or value only. Variables that always contain only one number or value can be compared using an equals sign, whereas this doesn't work for variables containing more information.
When comparing strings, we use the `equals` command, which is related to string variables.

```java
String text = "a string";
String anotherText = "another string";

System.out.println(text.equals("a string")); // true
System.out.println(text.equals(anotherText)); // false
```

The expression of a conditional statement may consist of multiple parts, in which the logical operators and `&&`, or `||`, and not `!` are used.
An expression consisting of two expressions combined using the and-operator is true, if and only if both of the combined expressions evaluate to true.
An expression consisting of two expressions combined using the or-operator is true, if either one, or both, of the combined expressions evaluate to true.
The not-operator is used for changing the boolean value from true to false, or false to true.

```java
int number = 7;

System.out.println(number >= 5 && number <= 10); // true
System.out.println(number < 0 || number > 5); // true
System.out.println(!(number > 4)); // false
```

The parsing of conditional statements stops at the first condition that is true. We should first find the **most demanding condition**, and implement it. After that, we would implement the other conditions.

---

### Programming in our society
As services become based on software, their inherent complexity becomes hidden to us. Software professionals are the architects of digital services. It's the responsibility of those of us who study computer science and engineering to implement these systems in a way that ensures that they function as well as they can for intended users and also for those not familiar with similar systems.

---
