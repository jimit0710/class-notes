---
sidebar_position: 9
---

# Unit Testing

*Unit testing breaks the program down into the smallest bit of code, usually function-level, and ensures that the function returns the value one expects. By using a unit testing framework, the unit tests become a separate entity which can then run automated tests on the program as it is being built.*

#### Basic Example

```csharp
namespace MyFirstUnitTests;

public class UnitTest1
{
    int Add (int x, int y) 
    {
        return x + y;
    }

    [Fact]
    public void Test1()
    {
        Assert.Equal(4, Add(2, 2));
    }

    [Theory]
    [InlineData(3)]
    [InlineData(5)]
    [InlineData(6)]
    public void MyFirstTheory(int value)
    {
        Assert.True(IsOdd(value));
    }

    bool IsOdd(int value)
    {
        return value % 2 == 1;
    }
}
```

- [Fact] attribute is used by the xUnit.net test runner to identify a ‘normal’ unit test - a test method that takes no method arguments.

- [Theory] attribute expects one or more DataAttribute instances to supply the values for a Parameterized Test’s method arguments.