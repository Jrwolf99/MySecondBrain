---
tags:
- programming
- notprocessed
---
# Abstract classes

In [[Java MOC]], it is impossible to achieve abstraction without using the `abstract` keyword. The abstract keyword can be used with the _methods_ and _classes_ only.

### Abstract Method
Always decared inside of abstract classes or interfaces.

**Rules**

1. In contrast to a concrete/normal [[Java MOC]] method an **abstract method** does not have a body/definition i.e. it only has a declaration or method signature inside an _abstract class or an interface_.

2. An **abstract method** can only be declared inside an _abstract class_ or an _interface_.

3. In other words, it can be said that to contain any **abstract method** in its implementation, a class has to be declared as an _abstract class_ because _non-abstract classes_ **cannot** have abstract methods.

4. An _abstract method_ **cannot** be declared _private_ as it has to be implemented in some other class.

**Example**
```java
public abstract void methodName(parameter(s));
```


### Abstract Class
Declared with the keyword `abstract`

**Rules**

1. An abstract class could have some abstract methods, but it isn't necessary. 

2. normal methods can be implemented.

3. An abstract class cannot be instantiated. Instead, to use them, you inherit from them. 

4. If a class inherits from the abstract class, it MUST IMPLEMENT ALL ABSTRACT METHODS that were declared in the parent abstract class. 





### Example

```java
abstract class Animal {

  public abstract void makeSound();

  public void move() {
    System.out.println(getClass().getSimpleName()+" is moving");
    //getClass().getSimpleName() is an inbuilt functionality of Java
    //to get the class name from which the method is being called
  }
  
}

class Dog extends Animal {

    @Override
    public void makeSound() {
    System.out.println("Woof Woof...");
  }
  
}

class Cat extends Animal {

    @Override
    public void makeSound() {
    System.out.println("Meow Meow...");
  }
  
}

class Sheep extends Animal {

    @Override
    public void makeSound() {
    System.out.println("Baa Baa..");
  }
  
}

class Main {
  
  public static void main(String args[]) {
    // Creating the objects
    Animal dog = new Dog();  
    Animal cat = new Cat();
    Animal sheep = new Sheep();

    dog.makeSound();    // Calling methods from Dog
    dog.move();

    cat.makeSound();    // Calling methods from Cat
    cat.move();

    sheep.makeSound();  // Calling methods from Sheep
    sheep.move();
  }
  
}
```


