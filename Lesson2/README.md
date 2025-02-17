# Lesson 2: Object-Oriented Programming (OOP) in C#

## Introduction

In this lesson, you'll learn about the core principles of Object-Oriented Programming (OOP) in C#. OOP is a programming paradigm that organizes code into reusable and modular units using **classes** and **objects**. The key concepts covered in this lesson include:

- **Classes and Objects** – Defining blueprints for creating objects.
- **Properties and Methods** – Encapsulating data and behavior.
- **Encapsulation, Inheritance, and Polymorphism** – Fundamental OOP principles.
- **Constructors and Static Members** – Special methods and shared class members.

By the end of this lesson, you will be able to create and work with C# classes effectively.

---

## Step 1: Understanding Classes and Objects

A **class** is a template for creating objects. An **object** is an instance of a class.

### Example:

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public void DisplayDetails()
    {
        Console.WriteLine($"Name: {Name}, Age: {Age}");
    }
}
```

---

## Step 2: Encapsulation, Inheritance, and Polymorphism

### Encapsulation

Encapsulation is the practice of keeping fields private and exposing them via properties or methods.

```csharp
public class BankAccount
{
    private double balance;

    public double Balance
    {
        get { return balance; }
        private set { balance = value; }
    }

    public void Deposit(double amount)
    {
        if (amount > 0)
            balance += amount;
    }
}
```

### Inheritance

Inheritance allows a class to inherit members from another class.

```csharp
public class Student : Person
{
    public string StudentId { get; set; }

    public void ShowStudentDetails()
    {
        DisplayDetails();
        Console.WriteLine($"Student ID: {StudentId}");
    }
}
```

### Polymorphism

Polymorphism enables a method to behave differently based on the object that invokes it.

```csharp
public class Teacher : Person
{
    public string Subject { get; set; }

    public void DisplayDetails()
    {
        Console.WriteLine($"Name: {Name}, Age: {Age}, Subject: {Subject}");
    }
}
```

---

## Step 3: Using Constructors and Static Members

### Constructors

Constructors initialize class objects when they are created.

```csharp
public class Car
{
    public string Model { get; }

    public Car(string model)
    {
        Model = model;
    }
}
```

### Static Members

Static members belong to the class rather than instances.

```csharp
public class MathUtility
{
    public static double Pi = 3.14159;
}
```

---

## Challenge: Create a `Person` and `Student` Class

### Instructions:

1. Create a `Person` class with properties **Name** and **Age**.
2. Add a method `DisplayDetails()` to print the person’s details.
3. Extend the `Person` class to create a `Student` class.
4. Add a property `StudentId` to `Student`.
5. Override `DisplayDetails()` in `Student` to display the student’s ID.

### Expected Output:

```plaintext
Name: John Doe, Age: 20
Student ID: S12345
```

### Sample Solution:

```csharp
class Program
{
    static void Main()
    {
        Student student = new Student
        {
            Name = "John Doe",
            Age = 20,
            StudentId = "S12345"
        };

        student.DisplayDetails();
    }
}
```

---

### 🎯 Congratulations! You have successfully implemented OOP concepts in C#. 🚀
