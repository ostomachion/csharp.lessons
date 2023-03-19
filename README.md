# C# Cheatsheet

## Initial Setup

### Installing Visual Studio

[Download page](https://visualstudio.microsoft.com/)

If you're on Windows (preferable), download and install Visual Studio Community 2022. All the defaults are probably fine. You can adjust settings and install additional components later if needed.

### Creating a Project

1. Launching Visual Studio.
2. Click <kbd><samp>Create a new project</samp></kbd>.
3. On the next screen, select the <kbd><samp>Console App</samp></kbd> template (not <kbd><samp>Console App (.NET Framework)</samp></kbd>) and click <kbd><samp>Next</samp></kbd>.
4. On the next screen, enter a name for your project in the <kbd><samp>Project name</samp></kbd> field (e.g., <kbd>HelloWorld</kbd>) and click <kbd><samp>Next</samp></kbd>. The defaults are fine for the other fields.
5. On the last screen, select <kbd><samp>.NET 7.0 (Standard Term Support)</samp></kbd> and click <kbd><samp>Create</samp></kbd>.

Visual Studio will create a new solution and project with a file called <samp>Program.cs</samp> with the following contents:

```csharp
// See https://aka.ms/new-console-template for more information
Console.WriteLine("Hello, World!");
```

### Running a program

There are multiple ways to run the code in the project:

- <kbd><kbd><samp>Debug</samp></kbd>-&gt;<kbd><samp>Start Debugging</samp></kbd></kbd>
- The solid "Play" ⏵ icon button
- The keyboard shorcut <kbd>F5</kbd>

Visual Studio will run your program in a console window with output similar to the following:

```
Hello, World!

C:\Users\user\source\repos\HelloWorld\HelloWorld\bin\Debug\net7.0\HelloWorld.exe (process 5555) exited with code 0.
To automatically close the console when debugging stops, enable Tools->Options->Debugging->Automatically close the console when debugging stops.
Press any key to close this window . . .
```

### Examining Program.cs

The Console app template contains only two lines (well, three if you count the blank line at the end).

```csharp
// See https://aka.ms/new-console-template for more information
```

The first line is a <b>comment</b>. Comments start with two forward slashes `//` and continue to the end of the line.
Comments can be used to add notes to programs and do not affect the program at all.

```csharp
Console.WriteLine("Hello, World!");
```

The second line tells the program to write the line <samp>Hello, World</samp> to the console output.
For now, just know that this is the pattern to write to the console. Try replacing <samp>Hello, World</samp> with some other text and re-running the program.

## Basic Values and Types

C# provides multiple basic types to represent data.

#### Logical Values
C# has a type called `bool` (short for Boolean) to represent things that are true or false. The literal values are `true` and `false`.

There are multiple operators that can be applied to Boolean values. The "and" operator, written `&&`, returns true only if both operands are true. The "or" operator, written `||`, returns true if either (or both) of its operands is true. The "not" operator, written `!`, returns true if its operand is false and vice versa.

### Textual Data

Textual data is represented by a type called `string`. String literals are written as text between double quotes, for example, `"Hello, World!"`.

Strings can be added together using the `+` operator.

```csharp
Console.WriteLine("foo" + "bar"); // foobar
```

Strings can be compared with the following operators:
- `==`: Equal to
- `!=`: Not equal to
```csharp
Console.WriteLine("Hello" == "World"); // false
Console.WriteLine("Hello" != "World"); // true
```

#### Whole Numbers

Integers are represented by a type called `int`. The `int` type represents 32-bit integer, which means that it can represent any value between -2,147,483,648 and 2,147,483,647, which is more than enough for most purposes. Integer literals are written without commas. For example, `42`, `10000`, and `-1`. If you want to separate the digits, you can use underscore characters, for example, `1_000_000`.

Integers can be added, subtracted, and multiplied using the `+`, `-`, and `*` operators. They can also be divided using the `/` operator, but note that the result will also be an integer, so the result will be rounded toward 0.

```csharp
Console.WriteLine(1 + 2); // 3
Console.WriteLine(10 - 6); // 4
Console.WriteLine(25 * 4); // 100
Console.WriteLine(20 / 3); // 6
```

Integers can be compared with the following operators:
- `<`: Less than
- `>`: Greater than
- `==`: Equal to
- `!=`: Not equal to
- `<=`: Less than or equal to
- `>=`: Greater than or equal to

```csharp
Console.WriteLine(1 < 2); // true
Console.WriteLine(1 > 2); // false
Console.WriteLine(1 == 2); // false
Console.WriteLine(1 != 2); // true
Console.WriteLine(1 <= 2); // true
Console.WriteLine(1 >= 2); // false
```

#### Decimal Numbers

Decimal numbers are represented by a type called `double`. The `double` type reprsents "double-precision floating point numbers" but don't worry about what that means right now, but the type can represent decimal values between approximately -1.8×10^308 and 1.8×10^308, and decimals as small as 4.94×10^-324. Double literals are written in the same way as integers, but include a decimal point and digits after the decimal point. For example, `3.14`, `2.0`, `-123.456789`.

Doubles can be added, subtracted, multiplied, and divided using the `+`, `-`, `*`, and `/` operators. If one operand is an integer and the other is a double, the result will be a double.

```csharp
Console.WriteLine(1.2 + 2.3); // 3.5
Console.WriteLine(3.14 - 0.14); // 3.0
Console.WriteLine(0.5 * -2.25); // -1.125
Console.WriteLine(3.14 / 2) // 1.57
```

Doubles can be compared with the following operators:
- `<`: Less than
- `>`: Greater than
- `==`: Equal to
- `!=`: Not equal to
- `<=`: Less than or equal to
- `>=`: Greater than or equal to

```csharp
Console.WriteLine(3.14 < 6.28); // true
Console.WriteLine(3.14 > 6.28); // false
Console.WriteLine(3.14 == 6.28); // false
Console.WriteLine(3.14 != 6.28); // true
Console.WriteLine(3.14 <= 6.28); // true
Console.WriteLine(3.14 >= 6.28); // false
```

Be careful with double values as they may not be exact due to the way they are encoded.

```csharp
Console.WriteLine(0.1 + 0.1 + 0.1); // 0.30000000000000004
```

