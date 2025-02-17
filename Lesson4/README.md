H# Lesson 4: Introduction to .NET Console Applications

## Introduction

In this lesson, you will learn how to create and work with **.NET Console Applications**. Console apps are simple text-based programs that are great for learning the fundamentals of C# and .NET.

Key topics covered in this lesson:

- **Setting up a .NET project**
- **Using the .NET CLI to build and run applications**
- **Reading from and writing to files**

By the end of this lesson, you will be able to set up a .NET project, work with the CLI, and handle file input and output (I/O) in C#.

---

## Step 1: Setting Up a .NET Console Application

### Create a new console application using the .NET CLI:

1. Open a terminal or command prompt.
2. Run the following command:

```bash
dotnet new console -n MyConsoleApp
```

This creates a folder named `MyConsoleApp` with the basic structure of a console application.

3. Navigate into the project directory:

```bash
cd MyConsoleApp
```

---

## Step 2: Building and Running Your Application

### Build the application:

```bash
dotnet build
```

### Run the application:

```bash
dotnet run
```

You should see the default "Hello, World!" output.

---

## Step 3: Reading from and Writing to Files

### Reading from a File:

```csharp
string path = "input.txt";
if (File.Exists(path))
{
    string content = File.ReadAllText(path);
    Console.WriteLine("File Content:");
    Console.WriteLine(content);
}
else
{
    Console.WriteLine($"File {path} not found.");
}
```

### Writing to a File:

```csharp
string outputPath = "output.txt";
File.WriteAllText(outputPath, "Hello, this is a test!");
Console.WriteLine("Data written to output.txt");
```

---

## Challenge: Build a Console App That Processes a Text File

### Instructions:

1. Create a console application.
2. Create a text file named `input.txt` with some sample text.
3. Read the contents of the file.
4. Process the data – for example, **count the number of words** in the file.
5. Display the word count in the console.

### Expected Output:

```plaintext
File contains 42 words.
```

---

### Sample Solution:

```csharp
class Program
{
    static void Main()
    {
        string path = "input.txt";

        if (!File.Exists(path))
        {
            Console.WriteLine($"File {path} not found.");
            return;
        }

        string content = File.ReadAllText(path);
        int wordCount = content.Split(' ', StringSplitOptions.RemoveEmptyEntries).Length;

        Console.WriteLine($"File contains {wordCount} words.");
    }
}
```

---

## Running Your Challenge Solution

1. Create `input.txt` in the root folder of your project and add some text.
2. Run your app:

```bash
dotnet run
```

---

### 🎯 Awesome work! You’ve built your first .NET console application and worked with files. 🚀
