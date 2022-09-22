---
sidebar_position: 7
---

# C# Types

```csharp
public class Program
{
    public static void Main (string[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

## Common Type System

The CTS defined two broad families of types in .NET. These are the "First-class citizens" of .NET.

:::note
A "first-class citizen" in a programming language is a way of saying "this is a thing a variable can refer to". First class citizens can have a name.
:::

### Value Types

Value types have their memory managed automatically and their life and scope is predictable.

The "value" lives on the stack. It is automatically removed from the stack when the variable goes out of scope.

Value types are `structs` in C#

### Reference Types

Reference types have values that live on the "managed" heap.

The stack has a reference to the value on the heap.

The memory is allocated automatically, and de-allocated using a generational garbage collector algorithm.

Memory is deallocated in a non-deterministic way. That means you can't _know_ when an value is removed from the heap.

This is known as "non-deterministic finalization".

Reference types are `class`es in C#.
