# Lesson 5: Error Handling and Debugging in C#

## Introduction

In this lesson, you will learn how to manage errors and debug your applications effectively. Writing robust applications means anticipating potential issues and handling them gracefully.

Key topics covered in this lesson:

- **Exception Handling**: Using `try`, `catch`, and `finally` blocks.
- **Debugging Techniques**: Using breakpoints, step-through execution, and watching variables in **Visual Studio** or **VS Code**.

By the end of this lesson, you will know how to handle errors and debug your C# console applications confidently.

---

## Step 1: Exception Handling

**Exceptions** are errors that occur during program execution. You can handle exceptions using `try`, `catch`, and `finally` blocks.

### Basic Structure:

```csharp
try
{
    // Code that may throw an exception
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
finally
{
    // Optional block that always runs
    Console.WriteLine("Execution completed.");
}
```

### Example:

```csharp
try
{
    int number = int.Parse("abc"); // This will throw a FormatException
}
catch (FormatException ex)
{
    Console.WriteLine("Invalid number format.");
}
catch (Exception ex)
{
    Console.WriteLine($"An error occurred: {ex.Message}");
}
finally
{
    Console.WriteLine("Program finished.");
}
```

---

## Step 2: Debugging Techniques

### In **Visual Studio**:

- **Set Breakpoints**: Click in the margin next to the line number.
- **Start Debugging**: Press `F5` to start, or `Ctrl + F5` to run without debugging.
- **Step Through Code**:
  - `F10` – Step Over (execute line but skip into methods)
  - `F11` – Step Into (enter methods)
  - `Shift + F5` – Stop debugging
- **Watch Variables**: Hover over variables to see their values during debugging.

### In **VS Code**:

- **Install C# Extension** if you haven’t already.
- **Set Breakpoints**: Click next to line numbers.
- **Run Debugging**: Press `F5` or click **Run and Debug** in the sidebar.
- **Step Over (F10)**, **Step Into (F11)**, **Stop (Shift + F5)** – same as Visual Studio.

---

## Challenge: Handle Invalid Input in a Previous Console App

### Instructions:

1. Take the **word-count console app** from **Lesson 4**.
2. Modify it to ask the user for a file name.
3. Handle the following cases using **exceptions**:
   - **File Not Found**.
   - **Empty File Name**.
   - **Any other unexpected errors**.
4. Display helpful error messages and ensure the app doesn’t crash.

---

### Expected Output Example:

```plaintext
Enter the file name: input.txt
File contains 42 words.
```

**OR (Invalid Input Example)**:

```plaintext
Enter the file name:
Error: File name cannot be empty.
```

---

## Sample Solution:

```csharp
class Program
{
    static void Main()
    {
        try
        {
            Console.Write("Enter the file name: ");
            string fileName = Console.ReadLine();

            if (string.IsNullOrWhiteSpace(fileName))
                throw new ArgumentException("File name cannot be empty.");

            if (!File.Exists(fileName))
                throw new FileNotFoundException($"File '{fileName}' not found.");

            string content = File.ReadAllText(fileName);
            int wordCount = content.Split(' ', StringSplitOptions.RemoveEmptyEntries).Length;

            Console.WriteLine($"File contains {wordCount} words.");
        }
        catch (ArgumentException ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
        catch (FileNotFoundException ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Unexpected error: {ex.Message}");
        }
        finally
        {
            Console.WriteLine("Program execution completed.");
        }
    }
}
```

---

## Testing Your App

1. Create `input.txt` or any text file.
2. Run your app:

```bash
dotnet run
```

3. Enter different file names (correct and incorrect) to test exception handling.

---

### 🎯 Great job! You can now handle errors and debug your console applications like a pro. 🚀
