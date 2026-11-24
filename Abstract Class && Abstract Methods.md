# Abstract Classes & Abstract Methods in Java

> A beginner-friendly explanation, like you're 5 😊

## Table of Contents

1. [Imagine a family of animals](#1-imagine-a-family-of-animals-)
2. [Abstract class = a general plan](#2-abstract-class--a-general-plan)
3. [Abstract method = a rule for children](#3-abstract-method--a-rule-for-children)
4. [The children do their jobs](#4-the-children-do-their-jobs)
5. [Abstract class vs abstract method](#5-abstract-class-vs-abstract-method)
6. [Three important rules](#6-three-important-rules)
7. [Mini test](#7-mini-test)
8. [Remember this](#remember-this)

---

## 1. Imagine a family of animals 🐶🐱🐰

We have a dog, a cat, and a rabbit. They are all animals, but they make different sounds:

- 🐶 Dog says **"Woof!"**
- 🐱 Cat says **"Meow!"**
- 🐰 Rabbit says **"Squeak!"**

Imagine we want to create a general plan for all animals. We know every animal should be able to make a sound, but we do not know **which** sound. This is where an **abstract class** comes in.

---

## 2. Abstract class = a general plan

An abstract class is like a general plan (blueprint) that other classes can use.

```java
public abstract class Animal {

}
```

In simple words:

| Word | Meaning |
|---|---|
| `public` | other classes can access it |
| `abstract` | this is an abstract class |
| `class` | we are creating a class |
| `Animal` | the name of our class |

Think of `Animal` as a **parent**. It tells its child classes what they should have or do.

---

## 3. Abstract method = a rule for children

Now we want every animal to make a sound. But we do not know which sound! So inside the `Animal` class we write:

```java
public abstract class Animal {

    abstract void makeSound();

}
```

The line `abstract void makeSound();` is an **abstract method**.

Imagine `Animal` is telling its children:

> "Every one of you **MUST** have a `makeSound()` method. But I will not tell you what to print. You decide!"

> [!NOTE]
> There are **no curly brackets `{ }`** after the method. We only declared that the method must exist. We have not written what it actually does.

---

## 4. The children do their jobs

**Dog class:**

```java
public class Dog extends Animal {

    @Override
    void makeSound() {
        System.out.println("Woof!");
    }

}
```

**Cat class:**

```java
public class Cat extends Animal {

    @Override
    void makeSound() {
        System.out.println("Meow!");
    }

}
```

**What happened?**

- `Dog` is a child of `Animal`.
- `extends Animal` means `Dog` inherits from `Animal`.
- `@Override` means `Dog` is providing its own version of the inherited method.
- `makeSound()` now has curly brackets and actual code.
- `Dog` and `Cat` each provide their own implementation of `makeSound()`.

---

## 5. Abstract class vs abstract method

| Abstract Class | Abstract Method |
|---|---|
| A blueprint for other classes | A rule that child classes must follow |
| Created using `abstract class` | Created using `abstract` before the method |
| Can contain methods with code | Has no method body |
| Cannot create its object directly | Must be implemented by a concrete child class |

**Example: one abstract class with two methods**

```java
public abstract class Animal {

    // Abstract method
    abstract void makeSound();

    // Normal method
    void sleep() {
        System.out.println("Sleeping...");
    }
}
```

Here:

- `makeSound()` = **abstract method** (no code/body)
- `sleep()` = **normal method** (has code/body)

> [!IMPORTANT]
> An abstract class does **NOT** need to have an abstract method. It can contain only normal methods too!

---

## 6. Three important rules

**1. You cannot create an object directly from an abstract class:**

```java
Animal animal = new Animal(); // ERROR
```

**2.** A normal (non-abstract) child class **must implement all** inherited abstract methods.

**3.** An abstract class can have **both** abstract methods and normal methods.

---

## 7. Mini test

**1. What is an Abstract Class?**

- [ ] A blueprint for other classes
- [ ] A method that prints text
- [ ] An object

<details>
<summary>Show answer</summary>

✅ **A blueprint for other classes.**

</details>

**2. What is an Abstract Method?**

- [ ] A method with curly brackets and code
- [ ] A method without a body
- [ ] A class

<details>
<summary>Show answer</summary>

✅ **A method without a body.**

</details>

**3. Who decides what sound the Dog makes?**

- [ ] Animal class
- [ ] Dog class
- [ ] Main class

<details>
<summary>Show answer</summary>

✅ **Dog class.**

</details>

**4. Can an Abstract Class have a normal method?**

- [ ] Yes
- [ ] No

<details>
<summary>Show answer</summary>

✅ **Yes.**

</details>

---

## Remember this!

> **An abstract class is a blueprint, and an abstract method is a rule inside that blueprint telling child classes which method they MUST implement.**

---

*Java Beginner Notes*
