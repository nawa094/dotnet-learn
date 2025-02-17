# Lesson 3: Collections and LINQ in C#

## Introduction

In this lesson, you will learn how to work with collections in C#, including:

- **Arrays** – Fixed-size collection of elements.
- **Lists** – Dynamic collection that can grow and shrink.
- **Dictionaries** – Key-value pairs for fast lookups.
- **LINQ (Language Integrated Query)** – A powerful tool to query and manipulate collections.

By the end of this lesson, you will be able to create, manipulate, and query collections effectively.

---

## Step 1: Working with Collections

### Arrays

An **array** is a fixed-size collection of elements of the same type.

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
Console.WriteLine(numbers[0]); // Output: 1
```

### Lists

A **List<T>** is a dynamic collection that can grow and shrink as needed.

```csharp
List<string> names = new List<string> { "Alice", "Bob", "Charlie" };
names.Add("David");
names.Remove("Bob");
Console.WriteLine(names.Count); // Output: 3
```

### Dictionaries

A **Dictionary<TKey, TValue>** stores key-value pairs for quick lookups.

```csharp
Dictionary<string, int> ages = new Dictionary<string, int>
{
    { "Alice", 25 },
    { "Bob", 30 }
};

Console.WriteLine(ages["Alice"]); // Output: 25
```

---

## Step 2: Introduction to LINQ

LINQ (Language Integrated Query) allows you to query collections in a concise and readable way.

### Common LINQ Operations:

#### Filtering:

```csharp
var evenNumbers = numbers.Where(n => n % 2 == 0);
```

#### Sorting:

```csharp
var sortedNames = names.OrderBy(n => n);
```

#### Selecting Specific Fields:

```csharp
var nameLengths = names.Select(n => n.Length);
```

#### Combining LINQ Operations:

```csharp
var longNames = names.Where(n => n.Length > 3).OrderBy(n => n);
```

---

## Challenge: Create a List of Products and Query with LINQ

### Instructions:

1. Create a `Product` class with **Name**, **Price**, and **Category** properties.
2. Create a `List<Product>` with at least 5 sample products.
3. Use LINQ to:
   - Filter products by **Category**.
   - Sort products by **Price** in ascending order.
4. Display the filtered and sorted products.

### Expected Output:

```plaintext
Name: ProductA, Price: 10, Category: Electronics
Name: ProductB, Price: 15, Category: Electronics
```

---

### Sample Solution:

```csharp
class Product
{
    public string Name { get; set; }
    public decimal Price { get; set; }
    public string Category { get; set; }
}

class Program
{
    static void Main()
    {
        List<Product> products = new List<Product>
        {
            new Product { Name = "Phone", Price = 500, Category = "Electronics" },
            new Product { Name = "Laptop", Price = 1200, Category = "Electronics" },
            new Product { Name = "Desk", Price = 200, Category = "Furniture" },
            new Product { Name = "Chair", Price = 150, Category = "Furniture" },
            new Product { Name = "Headphones", Price = 100, Category = "Electronics" }
        };

        var filteredProducts = products
            .Where(p => p.Category == "Electronics")
            .OrderBy(p => p.Price);

        foreach (var product in filteredProducts)
        {
            Console.WriteLine($"Name: {product.Name}, Price: {product.Price}, Category: {product.Category}");
        }
    }
}
```

---

### 🎯 Great job! You have successfully worked with collections and used LINQ to query data in C#. 🚀
