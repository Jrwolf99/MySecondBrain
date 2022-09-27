---
tags:
- programming
---
# Abstraction

"**The definition is somewhere else.**"

**Abstraction** in Object-Oriented Programming refers to showing only the essential features of an object to the user and hiding the inner details to reduce complexity.

More specifically, **Abstraction** is the process of putting your code into **"boxes"** so that the person looking at the higher level code doesn't know **"How it works"**, but instead only knows "**What it does**". 


**Whenever you want to use abstraction, the "Abstract class" or "Interface" is technically the part that only sees "What it does" and not "How it works".**

**Inside the inheritted class, i.e. the "parrot" class that implements the "canFly" interface, this is where the abstract methods are @Override and the actual implemenation occurs. **


### Example
All users only know and interact with their box, so therefore "abstraction" is used for them, but the admin can control and has access to everything, so it isn't used for him.
![[Pasted image 20220927110149.png]]


#### **Another Example**
Look at the Math.min() and Math.pow(): our program doesn't care about ***how*** it is implemented, it only cares about the fact that it can be implemented.
```java
class TestAbstraction {

  public static void main( String args[] ) {
    int min = Math.min(15,18);     //find min of two numbers
    double square = Math.pow(2,2); //calculate the power of a number
    System.out.println("The min of 15 & 18 is: " + min);
    System.out.println("The square of 2 is: " + square);
  }

  

}
```
**The definition is somewhere else.**



**How can we achieve abstraction in [[Java MOC]]?**
- [[Abstract classes]] : Abstraction can **ONLY** be implemented with the abstract keyword.
- [[Interface]]  : Interfaces use the `abstract` keywords and implement 100% abstraction.