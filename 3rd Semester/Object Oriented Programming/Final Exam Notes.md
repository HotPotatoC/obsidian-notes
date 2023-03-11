
# Object Oriented Programming

Object Oriented Programming is a paradigm widely used in the software development field. It revolves around the concept of blueprints and objects. A blueprint is what usually called a `class` in most programming languages contains **attributes** and **methods**.

An attribute is a set of variables defined in the class. A method is a function that is also defined in the class.

Each attribute and method are assigned with an access modifier that is: public, protected, and private.

- Public: attribute/method is accessible by the user
- Protected: attribute/method is only accessible by the derived class
- Private: attribute/method is only accessible inside the class itself and cannot be accessed outside by the user.

# OOP Concepts

We will discuss 5 main concepts

1. Inheritance
2. Abstraction
3. Polymorphism

## Inheritance

Inheritance is a method when an object extend or inherit attributes/methods from a parent/super class. Just like explained above regarding access modifiers, the derived class must obey the rules of the parent class and know which methods/attributes that can or can't be accessed.

Example in java:

```java
class A {
	public void foo() {
		System.out.println("A: foo");
	}

	private void secret() {
		System.out.println("Can only be accessed in A");
	}
}

class B extends A {
	public void bar() {
		System.out.println("B: bar");
	}
}

class Main {
	public static void main(String[] args) {
		B b = new B();

		b.bar(); // B: bar
		b.foo(); // A: foo
		b.secret(); // Error
	}
}
```

## Abstraction

Abstraction is a method to hide internal information of a class and only expose the important stuff to the outside world. A simple real-world example of Abstraction is a Car. You don't really need to know what happens internally when you hit the gas pedal or changing the gear. All you need to know is the superficial and yet sufficient information that is when you hit the gas pedal the car simply drives forward.

### Abstraction in Java

To achieve abstraction you need one abstract class and a derived class to inherit the abstract class.

To create an abstract class you use the `abstract` keyword for example:

```java
public abstract class Car {}
```

An abstract class **cannot be instantiated** and can only be **inherited**

#### Example in Java

```java
public abstract class Car {
	// Must implement & override in derived class
	public abstract void drive();
}

public class BMW extends Car {
	@Override
	public void drive() {
		System.out.println("Currently driving BMW");
	}
}

public class Toyota extends Car {
	@Override
	public void drive() {
		System.out.println("Currently driving toyota");
	}
}

public class Main {
	public static void main(String[] args) {
		BMW bmwCar = new BMW();
		bmwCar.drive();

		Toyota toyotaCar = new Toyota();
		toyotaCar.drive();
	}
}
```

### Interfaces

Interfaces are used to create a contract for subclasses where it's implementations are defined exclusively by the derived class. The derived class inherits interfaces using the `implements` keyword.

#### Example in Java

```java
public interface ImageFile {
	public void save(String path)
	public void load(String imagePath)
	public int pixelAt(int x, int y)
}

public class JPGImage implements ImageFile {
	public void save(String path) {
		... // Save JPG logic
	}

	public void load(String imagePath) {
		... // Load logic
	}

	public int pixelAt(int x, int y) {
		.. // pixelAt logic
	}
}

public class PNGImage implements ImageFile {
	public void save(String path) {
		... // Save PNG logic
	}

	public void load(String imagePath) {
		... // Load logic
	}

	public int pixelAt(int x, int y) {
		.. // pixelAt logic
	}
}
```

### Abstract vs Interfaces

Difference between Abstraction and Interfaces is a very popular discussion between beginners.

Abstract Classes are used to create a Base Class that can be reused by derived classes that inherits it. The derived class inherits abstract class using the `extends` keyword.

Interfaces are used to create a contract for subclasses where it's implementations are defined exclusively by the derived class. The derived class inherits interfaces using the `implements` keyword.

An abstract class can be defined with methods where these methods can provide its implementation, whereas interfaces can only define the method signature but not the implementation.

An Abstract or a Derived Class can only inherit 1 single class but can inherit multiple interfaces.

Interfaces can also inherit other interfaces using the `extends` keyword

Abstraction and interfaces can work together to design a robust convention in a development environment.

## Polymorphism

Polymorphism is an OOP concept where an object behaves differently in different situations. There are two ways to do polymorphism that is compile time polymorphism and runtime polymorpism.

Compile time polymorphism is achieved by doing **method overloading** where a class can have multiple methods with the same name but different parameters and data types. Another example of compile time polymorphism is parametric polymorphism also called generics.

Run time polymorphism is achieved by doing **method overriding** where a subclass can have a different implementation of a derived parent class' method

### Example in Java

```java
public abstract class Image {
	public void display() {
		System.out.println("Attempting to display image");
	}
}

public class JPEGImage extends Image {
	@Override
	public void display() {
		System.out.println("Displaying JPEG Image");
		// JPEG image display logic
	}
}

public class BMPImage extends Image {
	@Override
	public void display() {
		System.out.println("Displaying BMP Image");
		// BMP image display logic
	}
}
```

# Multithreading

Multithreading is a term used in computer science in which refers to the technique of running multiple processes simultaneously. In other words, executing two or more threads concurrently to maximize the utilization of the CPU. A thread is a lightweight, self-contained unit of execution that is used to accomplish multiple tasks concurrently within a program.

## Multithreading in Java

Java offers multithreading features to support for concurrent programming. To perform multithreading in Java, usually the `Thread` class is used. Some good uses of multithreading are for example:

- Online Games
- Web Servers (Handling hundreds of concurrent users)
- Performing time-consuming calculations

### Example of threads

```java
malassss
```