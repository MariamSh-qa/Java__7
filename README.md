
# Java OOP: Abstract Classes, Abstract Methods & Interfaces

## 1. Short Definitions

| Concept | Simple Explanation |
|---|---|
| **Abstract Class** | A blueprint / parent class for other classes. |
| **Abstract Method** | A method without a body that a concrete child class must implement. |
| **Interface** | A contract that tells a class which behaviors or methods it must provide. |

---

## 2. Main Differences

| Feature | Abstract Class | Interface |
|---|---|---|
| Keyword | `abstract class` | `interface` |
| Inheritance | `extends` | `implements` |
| Variables | Can have normal instance variables | Fields are `public static final` constants |
| Constructor | Yes | No |
| Normal methods | Yes | Yes (`default`, `static`, private methods) |
| Abstract methods | Yes | Yes |
| Multiple inheritance | A class can extend only ONE class | A class can implement MULTIPLE interfaces |

---

## 3. Things You MUST Remember

### Abstract Class
- Cannot create an object directly.
- Can have abstract and normal methods.
- Can have constructors and instance variables.
- A class inherits it using `extends`.

### Abstract Method
- Has no method body `{ }`.
- Ends with a semicolon `;`.
- Must be implemented by a concrete child class.
- If the child class is also abstract, it doesn't have to implement it yet.

### Interface
- A class uses `implements` to follow an interface.
- A class can implement multiple interfaces.
- Cannot create an interface object directly.
- Methods without bodies are implicitly `public abstract`.
- Variables are implicitly `public static final`.
- Can have `default` and `static` methods with code.

---

## 4. Code Examples

### Abstract Class

```java
public abstract class Animal {

    String name;

    abstract void makeSound();

    void sleep() {
        System.out.println("Sleeping");
    }
}
```

### Interface

```java
public interface Access {

    void checkAccess();

}
```

### Child Class Using Both

```java
public class Dog extends Animal implements Access {

    @Override
    void makeSound() {
        System.out.println("Woof!");
    }

    @Override
    public void checkAccess() {
        System.out.println("Access granted");
    }
}
```

---

## 5. The Most Important Java Rules

1. A class can `extend` only ONE class.
2. A class can `implement` MULTIPLE interfaces.
3. A class can extend one class AND implement multiple interfaces.
4. An abstract class cannot be instantiated directly.
5. A concrete child class must implement all inherited abstract methods.
6. An interface can be implemented by completely unrelated classes.
7. `@Override` indicates that you're providing an implementation of an inherited or interface method.

---

## 6. When Do We Use Them?

| Situation | What to Use |
|---|---|
| Several classes share common information and code | Abstract Class |
| Children need to implement a specific method differently | Abstract Method |
| Different classes need the same additional ability | Interface |

### Easy Memory Trick

- **Abstract Class** = WHAT WE SHARE.
- **Abstract Method** = WHAT CHILDREN MUST DO.
- **Interface** = WHAT ABILITIES WE CAN HAVE.

---

## 7. Quick Knowledge Check

**1. Which keyword is used to inherit an abstract class?**

- `implements`
- `extends` ✅
- `interface`

**2. Can a class implement 3 interfaces?**

- Yes ✅
- No

**3. Can an abstract class have a constructor?**

- Yes ✅
- No

**4. What happens if a normal child class doesn't implement an inherited abstract method?**

- It works normally.
- Compilation error. ✅
- Java ignores the method.

**5. What is an interface?**

- A contract defining behaviors. ✅
- A parent class with constructors.
- An object.

---

## Final Summary

- **Abstract Class** = WHAT WE SHARE.
- **Abstract Method** = WHAT CHILDREN MUST DO.
- **Interface** = WHAT ABILITIES WE CAN HAVE.

As a Java beginner, make sure you understand:
`extends`, `implements`, `abstract`, `@Override`, and the difference between abstract classes and interfaces.
