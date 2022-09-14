# Programmer Wisdom

These are some things I've received from others that have had a profound effect on how I write code. Where I remember where I got them from, I'll give attribution. Where I haven't, just assume it wasn't me. ;)

## "Write The Code You Wish You Had"

-- Corey Haines

```csharp
[HttpPost("/shoppingcart")]
public async Task<ActionResult> ProcessCart ([FromBody] Cart request) 
{
    // a bunch of validation and stuff here...

    // then I have to verify the credit card number...

    // "SPOT" - "Single Point of Truth"

    var isCreditCardValid = _creditCardValidator.Validate(request.CardInfo);
}

```

## Avoid Premature Abstraction

- Don't try to generalize a solution until you thoroughly understand the problem.

- Don't go create helper classes, methods, etc. until you know what you need.

:::tip "Never type Private, Always Refactor To it"
- Corey Haines
::::

## JHCI - "Just Hard Code It"

Deploying software is easy. don't prematurely build libraries, frameworks, configuration management goals until you know you need it.

## Code Duplication Stuff

- "Single Point of Truth" - each piece of business knowledge should exists in exactly one place in an application (Kent Beck)
- "DRY" - "Dont't Repeat Yourself"
- "Single Responsibility Principle" - "Each code module should have a single axis of change"
- Instead of Dry write "Moist Code".