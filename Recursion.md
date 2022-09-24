# Recursion

[Recursion](https://www.w3schools.com/java/java_recursion.asp) is used in programming to make a function call itself. this provides a way to break complicated problems down into simple problems which are easier to solve. 


### Example

Adding k until k exhausts down to 0.

```java
public class Main {
  public static void main(String[] args) {
    int result = sum(10);
    System.out.println(result);
  }
  public static int sum(int k) {
    if (k > 0) {
      return k + sum(k - 1);
    } else {
      return 0;
    }
  }
}
```