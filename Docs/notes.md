## TODO

steps:
1. set parent on all nodes
2. determine inheritance and class order
3. generate classes, structs, interfaces, delegates
4. generate methods, properties, and fields

* Chars unescape on parse, escape on output
* rework nullable and get rid of null?
* Events
* yield, async, await
* ranges?
* tuples?

## Min Syntax Notes

generic type constraints
```
class GenericClass{T {constraints}}

class GenericClass{T class}
```

allow named expressions in switch cases so you can do `is Token token`

allow method and property definitions in interfaces
