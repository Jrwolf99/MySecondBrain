---
tags:
- programming
---
# Aggregation

Aggregation follows the "[[has a]]" model.  This creates a parent-child relationship, where one class "owns" the other.

In **aggregation**, the lifetime of the owned object does not depend on the lifetime of the owner.

![[Pasted image 20220927121837.png]]

**In this example, a person has a country, but the country class is created outside of the scope of the person.**
```java
class Country {
  
    private String name;
    private int population;

    public Country(String n, int p) {
      name = n;
      population = p;
    }
    public String getName() {
      return name;
    }
  
}

class Person {
  
    private String name;
    private Country country; // An instance of Country class

    public Person(String n, Country c) {
      name = n;
      country = c;
    }

    public void printDetails() {
      System.out.println("Name: " + name);
      System.out.println("Country: " + country.getName());
    }
  
}

class Main {
  
  public static void main(String args[]) {
    Country country = new Country("Utopia", 1);
    {
      Person user = new Person("Darth Vader", country);
      user.printDetails();
    }
    // The user object's lifetime is over

    System.out.println(country.getName()); // The country object still exists!
  }
  
}
```