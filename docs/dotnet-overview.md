---
sidebar_position: 2
---
# Dotnet Overview


![Dotnet Overview](/img/dotnet.excalidraw.svg)


## What is it?

It is a platform for writing and running software from Microsoft.

If first was released in 2002.

It was originally the antithesis of Java.

:::note
What I mean is that Microsoft wanted .NET to run *only* on Windows, Java was originally (and still is) "cross platform"

Microsoft had to switch their approach with the advent of cloud computing, thus .Net Core
:::


## Dotnet Running

The **Common Language Runtime** is a managed runtime for your application. Your application is partially compiled to "Intermediate Language" and then "Just In Time (JIT) Compiled" to run at runtime.

.NET Applications compile to IL code.

.NET Applications compile to a format called an "Assembly"

- Assembly has the compiled IL code
- And a "database" of the *types* contained in that assembly.

(note: Assemblies are sort of like Jar files if you know Java).

Each **Project** in Visual Studio compiles to an Assembly.

A **Solution** is like a "workspace" and contain multiple projects.


## Terms you Should Memorize

:::note Common Language Runtime
The "CLR" - the program that runs your .NET Programs. Versions for Windows, Mac, and various Linux distributions are available
:::

:::note Intermediate Language
The language that .NET applications compile to (think Java Bytecode)
:::

:::note Common Type System
CTS. The type system in .NET that allows applications written in various languages (VB.NET, C#, etc.) interact with one another.
Has two basic types: Value Types and Reference Types.
Both Value Types and Reference Types are *user-definable*
:::
