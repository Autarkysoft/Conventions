# C# Coding Convention
The C# coding convetion is mostly the same as Microsoft's C# Coding Conventions found 
[here](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)
and coding guidelines used in .net core found [here](https://github.com/dotnet/corefx/tree/master/Documentation/coding-guidelines).  

The general rule is usually to follow "Visual Studio defaults".

## Layout Conventions
* Use tab for indentation
* Each line of code should contain about 100 characters and in case of overflow the rest should be on the new line 
with appropriate indentation.
* Use [Allman style](https://en.wikipedia.org/wiki/Indentation_style#Allman_style) braces (each brace begins on a new line)
* Braces could be removed for a single short line statement block but with proper indenting on its. If the block doesn't fit in
one line it still requires braces.
```csharp
if(b)
    throw new Exception();
if(b)
{
    Foo foo = fooEnumerable.SomeLinqThatTakesUpALotOfSpace()
                           .RestOfTheCode()
                           .SomeMore();
}
```
* Using parentheses in expressions (to group clauses) or in mathematical formulas 
(to indicate which operation should happen first) is preferred.
* Avoid spurious free spaces. For example avoid `if (someVar == 0)...`, where the dots mark the spurious free spaces.

## Spacing and code placing
* It is best if each member of a namespace is placed in a separate file with the same name as the member. 
* If the file contains more than one member (eg. 2 classes or 1 class 1 enum) they should be separated with at least 3 blank lines.
* Members of a class must be separated with at least one blank line.
* Each member of a class should be placed in the following order:
  * Constructors at the top. The order could be either alphabetical or with smallest one first.
  * Fields and properties should come right after constructor(s) after at least 2 blank lines and before methods.
  * Backing fields for properties should be placed close to the property itself and start with an underscore 
  (see naming convention for more information).
  * It is best if each member is sorted alphabetically. For example method called `Bar()` be placed above method called `Foo()`.
  But this rule is usually broken when methods rely on each other. For example `Foo()` comes first if `Bar()` calls it.
  * Destructors (if they exist) at the end of the file.
  * Any code that is called like a destructor (such as `Dispose()`) must be placed at the end.

## Comments and documentation
* It is nessasary for every public member (classes, methods, properties, fields,...) to have an xml documentation 
explaining what the member does and have any additional information that could help the caller. For example exceptions that could be 
thrown by the method. More information about xml documentation can be found 
[here](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/)
* It is preferred that the code also contains comments specially for complex algorithms and in cases where readability might have been
scarificed for performance gain.
* Comments are best be placed in a separate line.
* Comments should start with a space after the comment delimiter `//`, begin with uppercase, end with period, well formatted
and like lines of code they should not be longer than about 100 characters (the rest on next line).
```csharp
// Some long comment goes here explaining the code and the
// rest of it in case of overflow goes to next line.
// Comments may need additional indentation:
//    1. Case one
//    2. Case two
```
* Do not create formatted blocks of asterisks around comments.

## C# language specific guideline
* Namespace imports should be specified at the top of the file, outside of namespace declarations, and should be sorted alphabetically.
Remove any unused namespaces. 
* Avoid `this.` unless absolutely necessary
* Use `nameof` instead of hard coding the names as strings.
* Use [string interpolation](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/interpolated) 
to concatenate strings.
* Use `readonly` when possible.
* Visibility must be explicitly specified, even if it's the default and always come first. Example:
```csharp
// Correct
private string foo
public abstract class Foo {}
// Wrong
string foo;
abstract public class Foo {}
```
* Usage of `var` is avoided except for instantiation.
```csharp
// OK to use var
var foo = new Foo();
// Avoid using var
var foo = "some string";
var foo = GetSomething();
// Avoid even when the type looks obvious
var foo = GetString();
```
* Use object initializers to simplify object creation. `var employee = new Employee() { Name = "John Doe" };`




** Under construction **
