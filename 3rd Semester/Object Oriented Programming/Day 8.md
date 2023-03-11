# Day 8
Class: [[COMP6820001 - Object Oriented Programming]]
Session: 1
Topics: 
Date: 2022-10-01
Lecturer: [[D5320 - JULIAN WESLEY, S.Kom., M.TI]]

# Polymorphism

- Generic term that means "many shapes".
- Refer to the ability of a variable, function or object to take on multiple forms.

**Subtype**: a class defines a type, a type defined by a subclass is a subtype
**Supertype**: a type defined by its superclass. 

## Polymorphism Types

1. Trivial: Overloading
	- Handled at Compile-time
	- Static binding
2. Pure: Overriding
	- Handled at runtime
	- Dynamic binding

## Overriding

```java
public class Animal {
	public void print() {
		System.out.println("This is a method from Class Animal");
	}
}

public class Duck extends Animal {
	// Overrides print function with different implementation
	public void print() {
		System.out.println("This is Class Duck");
	}
}
```

## Overriding vs Overloading

**Overriding**

```java
public class Test {
	public static void main(String[] args) {
		A a = new A();
		a.p(10);
		a.p(10.0);
	}
}

class B {
	public void p(double i) {
		System.out.println(i * 2);
	}
}

class A extends B {
	// This method overrides the method in B
	public void p(double i) {
		System.out.println(i);
	}
}
```

**Overloading**

```java
public class Test {
	public static void main(String[] args) {
		A a = new A();
		a.p(10);
		a.p(10.0);
	}
}

class B {
	public void p(double i) {
		System.out.println(i * 2);
	}
}

class A extends B {
	// This method overloads the method in B
	public void p(int i) {
		System.out.println(i);
	}
}
```

## Polymorphism Example

```java
public class PolymorphismDemo {
	public static void main(String[] args) {
		Rectangle c = new Rectangle();
		System.out.println(c.computeArea());
	}
}

abstract class Shape {
	protected int x, y;
	public abstract double computerArea();
}

class Rectangle extends Shape {
	double width = 12, height = 20;
	public double computeArea() {
		return width * height;
	}
}

class Circle extends Shape {
	double radius = 20;
	public double computeArea() {
		return Math.PI * radius * radius;
	}
}
```

## Ad hoc Polymorphism

- Polymorphic functions that can be applied to different argument types known by the same name in a programming language.
- Ad hoc polymorphism is also known as a function overloading or operator overloading because a polymorphic function can represent a number of unique and potentially heterogeneous implementations depending on the type of argument it is applied to.

https://www.tutorialspoint.com/types-of-polymorphisms-ad-hoc-inclusion-parametric-and-coercion
https://www.geeksforgeeks.org/ad-hoc-inclusion-parametric-coercion-polymorphisms/