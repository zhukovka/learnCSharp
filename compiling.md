# COMPILING AND RUNNING THE PROGRAM

```cs
using System;
 
namespace Wrox
{
   public class MyFirstClass
   {
      static void Main()
      {
         Console.WriteLine("Hello from Wrox.");
         Console.ReadLine();
         return;
      }
   }
}
```
You can compile this program by simply running the C# command-line compiler (csc.exe) against the source file, like this:

```
csc First.cs
```

The `namespace` keyword declares the namespace with which your class should be associated. 
All code within the braces that follow it is regarded as being within that namespace. 
The using statement specifies a namespace that the compiler should look at to find any classes that are referenced in your code but aren’t defined in the current namespace. 
The reason for the presence of the using statement in the `First.cs` file is that you are going to use a library class, 
`System.Console`. The `using System;` statement enables you to refer to this class simply as Console (and similarly for any other classes in the System namespace). 
Without using, you would have to fully qualify the call to the Console.WriteLine method like this:

```cs
System.Console.WriteLine("Hello from Wrox.");
```

**It is important to realize that everything you do in C# depends on the .NET base classes.**

**All C# code must be contained within a class.**

**Every C# executable (such as console applications, Windows applications, and Windows services) must have an entry point — the Main() method (note the capital M).**

Note the format of method definitions in C#:

```
[modifiers] return_type MethodName([parameters])
{
   // Method body. NB. This code block is pseudo-code.
}
```
