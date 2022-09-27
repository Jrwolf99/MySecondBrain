---
tags:
- programming
- notprocessed
---
# Interface

Interfaces can be used to achieve **100%** [[abstraction]] as it contains the method signatures/abstract methods (What to be done) and no implementation details (how to be done) of these methods. 

In a way, interfaces satisfy the definition of abstraction.

The implementation techniques of the methods declared in an interface are totally up to the classes implementing that interface. 

An interface can be thought of as a **contract** to be fulfilled. 

A class that `implements` an interface has to `@Override` all the abstract methods declared in that very interface. 

**Rules**
- interfaces must be inherited, they can't be instantiated.
- if inherited, a class MUST implement all abstract methods. 
- Can't have constructors in ther interface.


**Terminology**

![[Pasted image 20220927111330.png | 500]]


**Example**
```java
// Base class Bird
class Bird {   

  // "eat" is a common trait of all birds so implemented in the base class
  public void eat() { 
    System.out.println(getClass().getSimpleName() + " is eating!");
  }
  
}

interface CanFly {
  // The method is by default abstract and public
  void flying();   
}

class Parrot extends Bird implements CanFly { 

  // If you don't implement the flying() you will get an error!
  // Overriding the method of CanFly interface
  @Override  
  public void flying() { 
    System.out.println("Parrot is Flying!");
  }
}

class Penguin extends Bird { 
  
  // Penguin cannot fly so not implementing CanFly
  public void walk() {
    System.out.println("Penguin is Walking!");
  }
  
}

class Main {

  public static void main(String[] args) {

    Parrot parrot = new Parrot();   
    Penguin penguin = new Penguin(); 

    parrot.eat();
    parrot.flying();

    System.out.println();   
    
    penguin.eat();
    penguin.walk();
    
  } // End of main()
  
} // End of Main class
```


**Advantages of using interfaces**
- Interfaces allow for 100% abstraction.
- Interfaces can be used to achieve _multiple inheritance_ because a class can "implements" multiple interfaces.
- **by the use of interfaces, one can break up complex designs and clear the dependencies between objects.** i.e. **MORE MODULARITY!!! WOOOO!**
