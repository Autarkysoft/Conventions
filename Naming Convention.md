# Naming Convention
The naming convention is mostly similar to Microsoft gneral naming conventions found 
[here](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/general-naming-conventions).  

* All _public_ member names must be easily readable and self-explanatory of what the member does even at the cost of longer names. 
For example from `Base58` encoder: `EncodeWithChecksum()` instead of `EncodeCheck()`.
* _Private_ members and local variables can have short and simple names, but readability is still preferred.
* Avoid using Hungarian notation.
* `PascalCasing` is used for namespaces, classes, structs, interfaces, methods, events, enums, properties and constants.
* `camelCasing` is used for parameter names, fields (public, protected, private,... with the exception of 
property backing field that should start with `_`).

## Usage of underscore (`_`)
Avoid using underscore in names. Some examples to avoid: `m_privateField`, `_privateField`, `Method_Name()`, `Some_Constant_Name`.  
Underscore must be used in the following cases and only in these cases:  
#### Property backing field
These are fields that are used by a property only:
```csharp
private int _foo;
public int Foo
{
   get => _foo;
   set => _foo = value;
}
```
#### Test names
Details below. Example: `Encode_ArgumentExceptionTest()` or `Encode_ArgumentException_Test()` but NOT `Encode_Test()`
for testing a method called `Encode`.

## Naming tests
* Test class should use the same name as the class/struct it is testing with the plural word `Tests` added to the end.
* Test class should be placed in the test project under the same namespace.
* Test methods use the same name as the method they are testing with the word `Test` added to the end.
* If there is more than one test for a method, use a descriptive name instead of adding numbers to the end.
* Any extra strings added to the name of the tests should be separated using `_`.
```csharp
namespace Autarkysoft.Encoders
{
  public class Base58
  {
     public string Encode(byte[] data){...}
  }
}
```
```csharp
namespace Tests.Encoders
{
  public class Base58Tests
  {
     public string EncodeTest(){...}
     public string Encode_EmptyBytesTest(){...}
     public string Encode_ExceptionTest(){...}
  }
}
```
## Naming benchmarks
* Similar to tests but the word `Benchmark` or `Bench` for short is used instead.
