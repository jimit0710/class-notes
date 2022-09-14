# Object Oriented Programming

## The idea is to marry state and behavior

```vb
Dim myName as String

set myName = "Jimit"

myName = UCase(myName)
```

```csharp
var myName = "Jimit";

myName = myName.ToUpper();

```

## To be an Object Oriented Language

1. Encapsulation
    - Comes from the root word "Capsule"
    - We hide how we do things - this alllows us to change it over time without impacting other code. 
    - This is how we get "abstraction" - "concept"
    - The bundling of data with the methods that operate on that data.
2. Polymorphism
3. Inheritance
4. Runtime Type Inspection (not all agree with this)

:::note What is OOP by Alan Kay
OOP to me means only messaging, local retention and proetction and hiding of state-process, and extreme late-binding of all things. It can be done in Smalltalk and in LISP. There are possible other systems in which this is possible, but I'm not aware of them.

[Source]
:::

- Information Hiding: Hide the internal representation, or state, of an object from the outside.

## Objects have:

### State
- Variables tha the object "owns"
- In .NET stateis in class level variables, we use the term `Fields` for these.

### Behavior
- Code that can be invoked that has something to do with the data (state) owned by that object.
- In .NET, the behavior is methods.
- Constructors
- Properties
- Events

### Properties in C#

Guidelines for deciding between properties and methods

1. Properties "imply" no computation
2. If you throw an exception on a property set or get, you are a jerk.
3. Once a property is set, then getting that property a bazillion times in a row should always return the same value.
    - so if I set `ah.Name = "Bob Smith"`, I should be able to read that over and over again and always get Bob Smith.


## Example

I have an object that represents a bank account

### State

Bank accounts have a current balance.

```csharp
public class BankAccount 
{
    private decimal _currentBalance = 0;

}
```

### Behaviors

We can make a deposit, and make a withdraw, and we can retrieve our balance.

```csharp
public class BankAccount 
{
    private decimal _currentBalance = 0;

    public void Deposit(decimal amount) 
    {
        _currentBalance += amount;
    }

    public void Withdraw(decimal amount) 
    {
        _currentBalance -= amount;
    }

    public decimal GetBalance() 
    {
        return _currentBalance;
    }
}
```