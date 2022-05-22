## TODO

* A block needs to have its own CurrentIndex state and interface so that ParseSpace can jump up to the parent and check children until one has content.
    * Loop will need to be `for CurrentIndex < Children.Count` so that once it's updated it picks up on the next item.
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

generic type constraints
```
class GenericClass{T [constraints]}

class GenericClass{T class}
```

`any` for System.Object

change parameter order to `name [modifiers] type [= value]`

allow named expressions in switch cases so you can do `is Token token`

allow method and property definitions in interfaces
