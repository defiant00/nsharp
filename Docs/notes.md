## TODO

* Chars unescape on parse, escape on output
* Events
* Generic constraints
* Generic in/out decorators for covariant/contravariant
* yield, async, await
* ranges
* properly parse anonymous functions as an expression or statement instead of assuming an expression

## Min Syntax Notes

Attributes
```
@Special
@SpecialAttribute
@Special("val")
@assembly:Special
```

do a first pass that determines inheritance and class order

make statement blocks on classes, interfaces, constructors, etc. optional

use `:` instead of `is` for lambdas
```
public fn Test() : Console.WriteLine("Hi")

x ? {
    1 : "one",
    2 : "two"
}

f = fn(x) : x * x

if x < 3 : Print("less than")

for x < 7 : Add()

for i in list : Print(i)
```

use `/fn` to end an anonymous function
* check if the first 3 characters match and the next character is not an identifier character
