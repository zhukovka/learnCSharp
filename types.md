# VALUE TYPES AND REFERENCE TYPES

Conceptually, the difference is that a value type stores its value directly, whereas a reference type stores a reference to the value.
C# has been designed this way because high performance is best served by keeping primitive types (such as int and bool) as value types, and larger types that contain many fields (as is usually the case with classes) as reference types. 
**If you want to define your own type as a value type, you should declare it as a struct.**

For example, when you declare an `int` in C#, you are actually declaring an instance of a .NET struct, `System.Int32`. This may sound like a small point, but it has a profound significance: It means that you can treat all the primitive data types syntactically, as if they were classes that supported certain methods. For example, to convert an int i to a string, you can write the following:

```cs
string s = i.ToString();
```

### Integer Types

```cs
long x = 0x12ab; //hex notation
uint ui = 1234U;
long l = 1234L;
ulong ul = 1234UL;
```
### Floating-Point Types

```cs
float f = 12.3F;
```

### The Decimal Type

The decimal type represents higher-precision floating-point numbers
Bear in mind, however, that decimal is not implemented under the hood as a primitive type, so using decimal has a performance effect on your calculations.

```cs
decimal d = 12.30M;
```

### The Character Type

Literals of type `char` are signified by being enclosed in single quotation marks — for example, `'A'`. If you try to enclose a character in double quotation marks, the compiler will treat this as a string and throw an error.

### The object Type

In C#, the object type is the ultimate parent type from which all other intrinsic and user-defined types are derived. You can use an object reference to bind to an object of any particular subtype; object references are also useful in reflection, when code must manipulate objects whose specific types are unknown.

### The string Type

```cs
string str1 = "Hello ";
string str2 = "World";
string str3 = str1 + str2; // string concatenation
```

Behind the scenes, a string object is allocated on the heap, not the stack; and when you assign one string variable to another string, you get two references to the same string in memory.
However, string differs from the usual behavior for reference types. For example, **strings are immutable**.

You can prefix a string literal with the at character `@` and all the characters after it will be treated at face value; they won’t be interpreted as escape sequences:

```cs
string filepath = @"C:\ProCSharp\First.cs";
```

