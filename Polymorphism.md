---
tags:
- programming
---
# Polymorphism

The word **Polymorphism** is a combination of two Greek words, **Poly** means _many_ and **Morph** means _forms_.

This is OOP's way of really reducing the amount of code that needs to be written.

**Say there were 4 shapes that "extended" the super class "Shape"**
![[Pasted image 20220927102400.png | 300]]


**Also say that we wanted to get the area of the shapes**
![[Pasted image 20220927102427.png | 300]]


**First, we would make the shape and declare the getArea method**
```java
// A simple Shape which provides a method to get the Shape's area
class Shape {
  public double getArea(){}
}
```

**Then we would make Rectangle "extend" Shape**
```java
// A Rectangle is a Shape with a specific width and height
class Rectangle extends Shape {   // derived form Shape class
  
  // Private data members
  private double width;
  private double height;
  
  // Constructor
  public Rectangle(double width, double height) {
    this.width = width;
    this.height = height;
  }
  
  // Public method to calculate Area
  public double getArea() {
    return width * height;
  }
}
```

**Then we would make Circle "extend" Shape**
```java
// A Circle is a Shape with a specific radius

class Circle extends Shape {

  // Private data member
  private double radius;

  // Constructor
  public Circle(double radius) {
    this.radius = radius;
  }

  // Public method to calculate Area
  public double getArea() {
    return 3.14 * radius * radius;
  }

}
```


### The benefit of this:
**We can now make Circles and Rectangles, and call the same "getArea" method for both of them in the same array.**
```java
class driver {

  

  public static void main(String args[]) {

    Shape[] shape = new Shape[2]; // Creating shape array of size 2
    shape[0] = new Circle(2); // creating circle object at index 0
    shape[1] = new Rectangle(2, 2); // creating rectangle object at index 1
    System.out.println("Area of the Circle: " + shape[0].getArea());

    System.out.println("Area of the Rectangle: " + shape[1].getArea());

  }

  

}
```