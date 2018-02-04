# VARIABLES

- [TYPE INFERENCE](#type-inference)
- [VARIABLE SCOPE](#variable-scope)
- [CONSTANTS](#constants)

You declare variables in C# using the following syntax:

```
datatype identifier;
```

For example:

```cs
int i;
i = 10;
int i = 10;
int x = 10, y =20;   // x and y are both ints
int x = 10;
bool y = true;       // Creates a variable that stores true or false
int x = 10, bool y = true;   // This won't compile!
```

Briefly, the C# compiler requires that any variable be initialized with some starting value before you refer to that variable in an operation.

Instantiating a reference object in C# requires use of the new keyword. You create a reference and then point the reference at an object allocated on the heap using the new keyword:

```cs
Something objSomething;
objSomething = new Something();   // This creates a Something on the heap
```

## TYPE INFERENCE

Type inference makes use of the var keyword. The syntax for declaring the variable changes somewhat. The compiler “infers” what the type of the variable is by what the variable is initialized to. For example:

```cs
int someNumber = 0;
```

becomes:

```cs
var someNumber = 0;
```

There are a few rules that you need to follow:

- The variable must be initialized. Otherwise, the compiler doesn’t have anything from which to infer the type.
- The initializer cannot be null.
- The initializer must be an expression.
- You can’t set the initializer to an object unless you create a new object in the initializer.

After the variable has been declared and the type inferred, the variable’s type cannot be changed. When established, the variable’s type follows all the strong typing rules that any other variable type must follow.

## VARIABLE SCOPE

The scope of a variable is the region of code from which the variable can be accessed. In general, the scope is determined by the following rules:

- A *field* (also known as a member variable) of a class is in scope for as long as its containing class is in scope.
- A *local* variable is in scope until a closing brace indicates the end of the block statement or method in which it was declared.
- A *local* variable that is declared in a for, while, or similar statement is in scope in the body of that loop.

Local variables with the same name can’t be declared twice in the same scope

For example, you can’t do this:

```cs
public static int Main()
{
   int j = 20;
   for (int i = 0; i < 10; i++)
   {
      int j = 30;   // Can't do this -- j is still in scope
      Console.WriteLine(j + i);
   }
   return 0;
}
```

## CONSTANTS

```cs
const int a = 100;   // This value cannot be changed.
```

They must be initialized when they are declared; and after a value has been assigned, it can never be overwritten.
The value of a constant must be computable at compile time. Therefore, you can’t initialize a constant with a value taken from a variable. If you need to do this, you must use a read-only field.
Constants are always implicitly static. However, notice that you don’t have to (and, in fact, are not permitted to) include the static modifier in the constant declaration.
