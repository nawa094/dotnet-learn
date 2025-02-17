# **Lesson 1: Introduction to C#**

Welcome to Lesson 1! In this lesson, you will learn the basics of C# programming. By the end of this lesson, you will be able to:

- Write and run a simple C# program.
- Understand variables, data types, and operators.
- Use control flow structures like `if/else` and loops.

---

## **Table of Contents**

- [**Lesson 1: Introduction to C#**](#lesson-1-introduction-to-c)
  - [**Table of Contents**](#table-of-contents)
  - [**Setting Up Your Environment**](#setting-up-your-environment)
  - [**Writing Your First C# Program**](#writing-your-first-c-program)
  - [**Variables and Data Types**](#variables-and-data-types)
    - [Example:](#example)
  - [**Operators**](#operators)
    - [Example:](#example-1)
  - [**Control Flow**](#control-flow)
    - [**If/Else Statements**](#ifelse-statements)
    - [**Loops**](#loops)
  - [**Challenge**](#challenge)
    - [**Challenge: BMI Calculator**](#challenge-bmi-calculator)
      - [Example Output:](#example-output)
  - [**Additional Resources**](#additional-resources)
  - [**Next Steps**](#next-steps)

---

## **Setting Up Your Environment**

Before you start coding, ensure you have the following installed:

1. **.NET SDK**: Download and install the [.NET SDK](https://dotnet.microsoft.com/download).
2. **Code Editor**: Use [Visual Studio Code](https://code.visualstudio.com/) or [Visual Studio](https://visualstudio.microsoft.com/).
3. **Terminal**: Familiarize yourself with your system's terminal or command prompt.

To verify your setup, run the following command in your terminal:

```bash
dotnet --version
```

You should see the installed .NET version.

---

## **Writing Your First C# Program**

1. Open your terminal and create a new console project:

   ```bash
   dotnet new console -o HelloWorld
   cd HelloWorld
   ```

   This creates a new folder called `HelloWorld` with a basic C# program.

2. Open the `Program.cs` file in your code editor. You’ll see the following code:

   ```csharp
   // Program.cs
   Console.WriteLine("Hello, World!");
   ```

3. Run the program:
   ```bash
   dotnet run
   ```
   You should see `Hello, World!` printed in the terminal.

---

## **Variables and Data Types**

Variables are used to store data. In C#, you must declare the type of a variable before using it. Here are some common data types:

- `int`: Integer (e.g., `42`)
- `double`: Floating-point number (e.g., `3.14`)
- `string`: Text (e.g., `"Hello"`)
- `bool`: Boolean (e.g., `true` or `false`)

### Example:

```csharp
int age = 25;
double price = 19.99;
string name = "Alice";
bool isStudent = true;
```

---

## **Operators**

Operators are used to perform operations on variables and values. Here are some common operators:

- **Arithmetic**: `+`, `-`, `*`, `/`, `%`
- **Comparison**: `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Logical**: `&&` (AND), `||` (OR), `!` (NOT)

### Example:

```csharp
int x = 10;
int y = 20;
int sum = x + y; // 30
bool isEqual = x == y; // false
```

---

## **Control Flow**

Control flow structures allow you to make decisions and repeat actions in your code.

### **If/Else Statements**

Use `if/else` to execute code based on a condition:

```csharp
int age = 18;
if (age >= 18)
{
    Console.WriteLine("You are an adult.");
}
else
{
    Console.WriteLine("You are a minor.");
}
```

### **Loops**

Use loops to repeat code. Here’s a `for` loop:

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine("Iteration: " + i);
}
```

---

## **Challenge**

Now it’s your turn to practice! Complete the following challenge to reinforce what you’ve learned.

### **Challenge: BMI Calculator**

Write a C# program that calculates the Body Mass Index (BMI) of a person. The program should:

1. Ask the user for their weight (in kilograms) and height (in meters).
2. Calculate the BMI using the formula:
   ```
   BMI = weight / (height * height)
   ```
3. Display the BMI and a message based on the result:
   - Underweight: BMI < 18.5
   - Normal weight: 18.5 <= BMI < 24.9
   - Overweight: BMI >= 25

#### Example Output:

```
Enter your weight in kg: 70
Enter your height in meters: 1.75
Your BMI is 22.86. You are normal weight.
```

---

## **Additional Resources**

- [C# Documentation: Getting Started](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/)
- [Microsoft Learn: C# Fundamentals](https://learn.microsoft.com/en-us/users/dotnet/collections/yz26f8y64n7k07)
- [W3Schools: C# Tutorial](https://www.w3schools.com/cs/)

---

## **Next Steps**

Once you’ve completed this lesson, move on to **Lesson 2: Object-Oriented Programming (OOP)** to learn about classes, objects, and more advanced C# concepts.

---

Happy coding! 🚀
