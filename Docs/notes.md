## TODO

* Chars unescape on parse, escape on output
* arrays with `arr` or `array` instead of special [] syntax
* rework nullable and get rid of null?
* Events
* Generic constraints
* Generic in/out decorators for covariant/contravariant
* yield, async, await
* ranges?
* tuples?
* properly parse anonymous functions as an expression or statement instead of assuming an expression

## Min Syntax Notes

modifiers as attributes

Attributes (no indicator needed, just check for identifiers)
```
public
assembly:Obsolete
Special
Special("thing")
Special(Flag = true)
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
class GenericClass{T {constraints}}

class GenericClass{T class}
```

allow named expressions in switch cases so you can do `is Token token`

allow method and property definitions in interfaces
