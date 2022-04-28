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

Loops
```
for i in 10
    ; 0-9

for i in myList
    ; iterate over myList

for i in myList
    Console.Write(i)
bet
    Console.Write(", ")

for i = 0, i < 7, i += 1
    ; normal for loop

for
    ; infinite loop

for i < 7
    ; while loop
```

Access modifiers - sane defaults (protected, final? see kotlin) and only keywords for differences (eg, no `protected`). Maybe `open` to not be `final` but abstract are always open?


implicit types wherever possible
