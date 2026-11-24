
# Java Interfaces

## 1. What is an Interface?

An **interface** is like a contract or a set of rules that a class promises to follow.

It tells a class **what methods it must have**, but usually does not provide the actual method code.

For example, imagine a remote control. Every TV must know how to respond to the power button, but different TVs can work differently.

In Java:
- An interface defines methods that a class must implement.
- A class uses `implements` to follow an interface.
- The class provides the actual code for the methods.

## 2. How to Create an Interface

```java
public interface Access {

    void checkAccess();

}
```

Explanation:

- `interface` creates an interface.
- `Access` is the interface name.
- `void checkAccess();` declares a method.
- The method has no body because the interface only declares what must be done.

## 3. How to Implement an Interface

```java
public class Admin implements Access {

    @Override
    public void checkAccess() {
        System.out.println("Admin has full access");
    }

}
```

Explanation:

- `implements Access` means Admin agrees to follow the Access interface.
- `@Override` indicates that we are implementing a method declared in the interface.
- `checkAccess()` contains the actual code.

## 4. Different Classes Can Implement the Same Interface

```java
public class Customer implements Access {

    @Override
    public void checkAccess() {
        System.out.println("Customer has limited access");
    }

}
```

Both Admin and Customer implement Access.

However, each class can have a different implementation of `checkAccess()`.

## 5. Calling Interface Methods in main()

```java
public class Main {

    public static void main(String[] args) {

        Admin admin = new Admin();
        admin.checkAccess();

        Customer customer = new Customer();
        customer.checkAccess();

    }
}
```

Output:

```text
Admin has full access
Customer has limited access
```

## 6. Important Interface Rules

1. Use `interface` to create an interface.
2. Use `implements` when a class implements an interface.
3. A class must implement all inherited abstract interface methods unless the class is abstract.
4. One class can implement multiple interfaces.
5. A class can extend only one parent class.
6. Interface abstract methods are implicitly `public abstract`.
7. Interface variables are implicitly `public static final` (constants).
8. Interfaces cannot be instantiated directly.

## 7. Implementing Multiple Interfaces

A class can implement more than one interface.

Example:

```java
public interface Access {
    void checkAccess();
}

public interface Login {
    void login();
}

public class Admin implements Access, Login {

    @Override
    public void checkAccess() {
        System.out.println("Access granted");
    }

    @Override
    public void login() {
        System.out.println("Admin logged in");
    }
}
```

Admin implements two interfaces: Access and Login.

## 8. Difference Between Abstract Class and Interface

| Abstract Class | Interface |
|---|---|
| Uses `abstract class` | Uses `interface` |
| A class extends it | A class implements it |
| Can have constructors | Cannot have constructors |
| Can have instance variables | Fields are constants by default |
| Can have abstract and normal methods | Can have abstract, default, static and private methods |
| A class can extend only one class | A class can implement multiple interfaces |

## 9. Remember

- `extends` = inherit from a class.
- `implements` = follow an interface.
- Interface = contract / rules.
- Abstract method = method without a body.
- A class implementing an interface must provide implementations for its abstract methods, unless that class is abstract.

**Easy way to remember:**

An interface tells a class WHAT it must do.

The class decides HOW to do it.
