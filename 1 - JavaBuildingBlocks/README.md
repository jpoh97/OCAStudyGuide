# 1. Java Building Blocks

## 1.1. Understanding the Java Class Structure

In Java programs, classes are the basic building blocks. When defi ning a class, you describe all the parts and characteristics of one of those building blocks. To use most classes, you have to create objects. An object is a runtime instance of a class in memory. All the various objects of all the different classes represent the state of your program.

### 1.1.1. Fields and Methods

Java classes have two primary elements: methods, often called functions or procedures in other languages, and fi elds, more generally known as variables. Together these are called the members of the class. Variables hold the state of the program, and methods operate on that state.

* The full declaration of a method is called a method signature.

### 1.1.2. Comments

There are three types of comments in Java. The first is called a single-line comment:
``` // comment until end of line ```
Next comes the multiple-line comment:
```
/* Multiple
 * line comment
 */
 ```
People often type an asterisk (*) at the beginning of each line of a multiline comment to make it easier to read, but you don’t have to. Finally, we have a Javadoc comment:
```
 /**
 * Javadoc multiple-line comment
 * @author Jeanne and Scott
 */
```
Examples:
```
/*
 * // anteater
 */
// bear
// // cat
www.allitebooks.com
Understanding the Java Class Structure 5
c01.indd 1½ 4/2014 Page 5
// /* dog */
/* elephant */
/*
 * /* ferret */
 */
 ```
The line with ferret is interesting in that it doesn’t compile. Everything from the fi rst /* to the fi rst */ is part of the comment, which means the compiler sees something like this:
``` /* */ */ ```

### 1.1.3. Classes vs Files
Java does not require that the class be public. For example, this class is just fine:
```
1: class Animal {
2:  String name;
3: }
```
You can even put two classes in the same file. When you do so, at most one of the classes in the file is allowed to be public. That means a file containing the following is also fine:
```
1: public class Animal {
2:  private String name;
3: }
4: class Animal2 {
5: }
```
If you do have a public class, it needs to match the filename. public class Animal2 would not compile in a file named Animal.java.

## 1.2. Writing a main() method

A Java program begins execution with its main() method. A main() method is the gateway between the startup of a Java process, which is managed by the Java Virtual Machine (JVM), and the beginning of the programmer’s code.

* To compile and execute this code, type it into a fi le called Zoo.java and execute the following:
```
$ javac Zoo.java
$ java Zoo
```
To compile Java code, the fi le must have the extension .java. The name of the file must match the name of the class. The result is a fi le of bytecode by the same name, but with a .class filename extension. Bytecode consists of instructions that the JVM knows how to execute.

* A nonstatic main() method might as well be invisible from the point of view of the JVM.
* In general, it’s good practice to use void for methods that change an object’s state. In that sense, the main() method changes the program state from started to finished. 
*  If you want spaces inside an argument, you need to use quotes as in this example:
```
$ javac Zoo.java
$ java Zoo "San Diego" Zoo
```
* All command-line arguments are treated as String objects, even if they represent another data type:
```
$ javac Zoo.java
$ java Zoo Zoo 2
```

## 1.3. Understanding Package Declarations and Imports
Java puts classes in packages. These are logical groupings for classes.
The import statement tells the compiler which package to look in to find a class.

### 1.3.1. Wildcards
``` import java.util.*; // imports java.util.Random among other things ```
In this example, we imported java.util.Random and a pile of other classes. The * is a wildcard that matches all classes in the package. Every class in the java.util package is available to this program when Java compiles it. 
* You might think that including so many classes slows down your program, but it doesn’t. **The compiler figures out what’s actually needed**. Which approach you choose is personal preference. Listing the classes used makes the code easier to read, especially for new programmers. Using the wildcard can shorten the import list.

### 1.3.2. Redundant Imports
