# N# - Min Syntax

Min is an indentation-based language inspired by Python, C#, Kotlin, and Go. Its main goal is to reduce typing and punctuation without sacrificing readability.

---

## Syntax

* [Anonymous Functions](#anonymous-functions)
* [Characters](#characters)
* [Comments](#comments)
* [Enumerations](#enumerations)
* [Escaped Characters](#escaped-characters)
* [Extensions](#extensions)
* [Fields](#fields)
* [Generics](#generics)
* [Identifiers](#identifiers)
* [If Statement](#if-statement)
* [Line Continuation](#line-continuation)
* [Methods](#methods)
* [Numbers](#numbers)
* [Properties](#properties)
* [Short Forms and Blocks](#short-forms-and-blocks)
* [Strings](#strings)
* [Types](#types)

## Other

* [Comparison with C#](#comparison-with-c)

---

## Anonymous Functions

### Short form
```
fn(x): x * x
fn(name): Console.WriteLine("Hello {name}")
```

### Long form
```
fn(x)
    var y = x * 2 + 7
    return y
/fn
```
\* _Anonymous functions_ are the only multi-line expression, which is why they require an ending `/fn`.

---

## Characters

Individual characters are surrounded by single quotes `'`. You can [escape characters](#escaped-characters) with `\`.
```
var c = 'c'
var newline = '\n'
```

---

## Comments

Comments in Min begin with `;`. Documentation comments begin with `;;`. Comments are single line statements, which means that they are _only_ valid in these scenarios:

* On their own line.
* In places that statements are allowed, like the short form of a [method definition](#methods).
* After an [enumeration](#enumerations) value.
```
; a comment on its own line
;; a documentation comment

fn MyMethod(): ; empty

enum MyEnum
    FirstValue ; this is the first value
```

---

## Enumerations

Enumerations are named values defined with `enum`. You can optionally provide an explicit numeric value and/or a comment as well.
```
public enum MyEnum
    FirstValue
    SecondValue = 3
    ThirdValue ; a value with a comment
```

---

## Escaped Characters

Escaped characters in a [character](#characters) or [string](#strings) begin with `\`.

Code       | Meaning
----       | -------
\n         | newline
\r         | carriage return
\t         | tab
all others | the escaped character

---

## Extensions

Extensions are declared with the `ext` modifier that takes a generic type. This modifier is valid on methods and properties contained within a `static` class. The method or property is declared as usual, and `this` is used to access the instance.
```
public static class MyClass
    public ext{str} fn Lower str: str.ToLower(this)

    public ext{str} fn Greet() str
        return "Hello {this}!"
```

---

## Fields

Fields are variables on classes or structs, so they are declared with `var`.
```
public class MyClass
    public var MyField str
```

---

## Generics

Generics are declared using `{}`.
```
var myList = new List{str}()

public class MyClass{T}
    public Property T
```

---

## Identifiers

Identifiers start with `_` or a letter, and all characters after the first can be a `_`, letter, or number.

You can prefix an identifier with a `` ` `` (grave accent) to use keywords as identifiers. The `` ` `` is not included in the identifier.

---

## If Statement

An if statement consists of an optional local variable and the condition, followed by the statements to execute if the condition is true. It can then optionally be followed by any number of `else if` statements, and/or a final `else`. Each `else if` statement may have its own optional local variable and condition.

Local variables are in scope for the `if` statement and any following `else if` and `else` statements.
```
if x < 7: DoSomething()

if x = CalculateAValue(), x < 7
    DoSomething()

if x < 3
    DoSomething()
else
    DoSomethingElse()

if x = CalculateVal1(), x < 7
    DoSomething(x)
else if y = CalculateVal2(), x < 3 and y == 5
    DoSomethingElse(x + y)
else
    Console.WriteLine("got {x} and {y}")
```

---

## Line Continuation

Line continuation automatically occurs if a line _ends_ with an opening bracket or operator, or if the next line _starts_ with a closing bracket or operator.

---

## Methods

Methods can be defined on classes and structs with `fn`. Valid modifiers for methods include visibility modifiers, `static`, and `open`. If the method in the base class is `open`, then the child class can override it with the `over` keyword.

### Method Header
```
[modifiers] fn name([parameters]) [return type]
```

### Short Form
```
; prints "hello"
public fn MyMethod(): Console.WriteLine("hello")

; returns the string "hello"
public fn MyMethod() str: "hello"
```

### Long Form
```
; prints "hello"
public fn MyMethod()
    Console.WriteLine("hello")

; returns the string "hello"
public fn MyMethod() str
    return "hello"
```

---

## Numbers

Numbers can be in decimal, binary, or hexadecimal format. Decimal numbers are written in the format `123` and `123.45`. Binary numbers are prefixed with `0b`, so `0b1001`. Hexadecimal numbers are prefixed with `0x`, with both uppercase and lowercase digits allowed such as `0x1abc` and `0x2DEF`.

---

## Properties

Properties are getter and/or setter functions on classes or structs, so they are declared using `fn`.
```
public class MyClass
    public fn MyProperty str
```

---

## Short Forms and Blocks

Most statements that accept an indented block of statements such as [methods](#methods) and [if statements](#if-statement), can instead be followed by a `:` and a single statement or expression. If the construct is one that returns a value, a supplied expression will be implicitly returned.
```
; this method returns 3
fn GetThree() int: 3

; this method prints to the console
fn PrintMessage(): Console.WriteLine("the answer is 42")

; if x < 7, call DoThing()
if x < 7: DoThing()
```

---

## Strings

Strings are surrounded by double quotes `"` and support interpolation by surrounding expressions with curly brackets `{}`. Along with supporting [escaped characters](#escaped-characters) using `\`, you can also enter a literal `"`, `{`, or `}` by doubling it within the string.
```
var myString = "Hello {name}"
var quote = "And she said, ""Hey!"""
var curlies = "Look, these are curly: {{ }}"
```

Multiline strings are supported through the `..` operator, which is equivalent to `System.Environment.NewLine`.
```
var multiline = "Hello {name}" ..
    "This is an example of the .. operator" ..
    "and multiline strings in Min."
```

---

## Types

---

## Comparison with C#

* String concatenation with `+` is not supported. `System.String.Concat` is still available if required.
* No `object` keyword. Use `System.Object` if an explicit object type is needed.
* The `++` and `--` operators do not exist, use `+= 1` and `-= 1`.
* `for`, `foreach`, and `while` are all represented by `for`.
* `for x in y` can accept an `IEnumerable` or a number for `y`.
* `switch` and `case` have been replaced by `if` and `is`, cases all have their own scope (local variables declared in a case are local to the case), and `break` is not required at the end.
* Extension is a modifier, and can be set on both methods and properties. While the same visibility rules apply as C#, you do not have to declare the instance variable, but can instead use `this`, or no qualifier - the same as in an actual instance method.
* `use`, the equivalent of C#'s `using`, does not have specific requirements beyond being a dotted set of identifiers. When resolving identifiers, the name is checked with the `use` value prepended. This means that you can just as easily `use` a specific class, namespace, or even enumeration.
* Constructors are declared with the name `new`, not the class name.
* The nullable type indicator comes before the base type, eg `?int`.
* Arrays are treated like any other generic type: `array{type}`. Multi-dimensional arrays are represented by name, with the format `array_dim{type}`, eg `array_3{str}` for a three dimensional array of strings.
* Names come before types, such as `myName str` or `guests List{str}`.
* And and or are spelled `and` and `or`, not `&&` and `||`.
