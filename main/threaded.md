---
tags:
- programming
---
# Threaded

Java being "Threaded" means that Java has "[threads](https://www.w3schools.com/java/java_threads.asp)" that allow a program to operate more eficiently by doin multiple things at the same time.

This is parallelism.

### creating a thread in Java

You can override the run() method:

```java
public class Main extends Thread {
  public void run() {
    System.out.println("This code is running in a thread");
  
```
