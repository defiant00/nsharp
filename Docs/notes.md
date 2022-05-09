## TODO

* expression statement blocks

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

```
MyClass.SubClass
    Property = val
    Method()
    AnotherSubClass
        Prop = val
        ["indexer"] += val
```

Modifiers in general should be allowing things.
    Default all to private/internal, so you pick what you share
    Default to final, you have to declare them open (abstract is always open)


implicit types wherever possible
