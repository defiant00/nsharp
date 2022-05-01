## TODO

* Strings and chars unescape on parse, escape on output
* Events
* Generic constraints
* Parameter decorators (out, ref, params, etc)
* single line anonymous functions parsing as an expression or statement based off of the resolved return type instead of just whether the return type was explicitly specified so you can `fn(x) is x * x` and it'll resolve as `return x * x` instead of an expression statement with no return

## Items

* Expressions
    * _ str literal
    * _ char literal
    * _ number literal
    * _ array literal
    * _ null literal
    * _ bool literal
    * _ field/property
    * _ method call
    * _ accessor
    * _ new
    * _ new array
    * _ binary op
    * _ unary op
    * _ is op
    * _ conditional
    * _ anonymous fn
    * _ default
    * _ typeof?
* Statements
    * file level
        * _ namespace
        * _ import
        * _ class def
        * _ interface def
        * _ struct def
        * _ enum def
        * _ delegate def
        * _ attributes
    * class level
        * _ class def
        * _ interface def
        * _ struct def
        * _ enum def
        * _ method def
        * _ constructor def
        * _ delegate def
        * _ field def
        * _ const def
        * _ property def
        * _ attributes
    * method level
        * _ var
        * _ const
        * _ using
        * _ assignment
        * _ if/else
        * _ switch
        * _ for
        * _ foreach
        * _ try/catch/finally
        * _ break
        * _ continue
        * _ return
        * _ base
        * _ attributes
        * _ throw
        * _ rethrow

## Min Syntax Notes

Attributes
```
@Special
@SpecialAttribute
@Special("val")
@assembly:Special
```


Access modifiers - sane defaults (protected, final? see kotlin) and only keywords for differences (eg, no `protected`). Maybe `open` to not be `final` but abstract are always open?


implicit types wherever possible
