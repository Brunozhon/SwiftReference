# Swift Reference

## Types

A type in Swift is like a blueprint. Think of a house's blueprint.

**Note:** You might be new to the syntax but I will cover it up later.

| Properties       | Methods           |
|------------------|-------------------|
| `floors`         | `buildHouse(at:)` |
| `isBuilded`      | `demolishHouse()` |
| `numberOfPeople` |                   |

You write it like this in Swift:

**Note:** Again, you might be new to the syntax but I will cover it up later.

```swift
struct House: Placable {
  var floors: [Floor]
  var isBuilded: Bool
  var numberOfPeople: Int
  func buildHouse(at location: Location) {
    place(self, at: location)
  }
  func demolishHouse() {
    delete(self)
  }
}
```

There are several types in Swift. They are:

- `String`
- `Int`
  - `Int8`
  - `Int16`
  - `Int32` (On a 32-bit platform, `Int` is equal to `Int32`)
  - `Int64` (On a 64-bit platform, `Int` is equal to `Int64`)
- `UInt`
  - `UInt8`
  - `UInt16`
  - `UInt32` (On a 32-bit platform, `Int` is equal to `Int32`)
  - `UInt64` (On a 64-bit platform, `Int` is equal to `Int64`)
- `Double`
- `Float`
- `Bool`

### String

A string can store any value.

```swift
"This is a string."
```

You store it in a variable.

> **Quick reference:**
> `var` is for values that can mutate. `let` is for values that cannot mutate.

```swift
let myString = "This is a string."
```

You can append strings using _string concentration_. String concetration means appending two or more strings together, like this:

```swift
"One, two," + " three!" // "One, two, three!"
let quotation = "I said, '" + myString + "'" // "I said, 'This is a string.'"
```

There's an even shorter way to add strings! You can use `\()` in a string and you're done! Well, not quite done yet, as you'll see...

```swift
"\(myString) But diffrent." // "This is a string. But diffrent."
```

You can make muitiline strings by including three double quotation marks (`"""`) at the beginning and end of your content. 

```swift
"""
\(myString)
But in multiple lines.
"""
/*
"""
This is a string.
But in multiple lines.
"""
*/
let banner = """
H
e
l
l
o

w
o
r
l
d!
"""
```

### Integers

An integer is a number literal with no decimals.

```swift
// Integer
183
// Not an integer
31.21
```

Unlike strings, integers can't span mulitple lines.

```swift
// Results in 1, 8, and 3. Not 183.
1
8
3
```

You can do addition, subtraction, multiplication, divison, and remainder in Swift.

```swift
let addition = 10 + 5 // 15
let subtraction = addition - 7 // 15 - 7 = 8
let multiplication = subtraction * 5 // 8 * 5 = 40
let divison = multiplication / 10 // 40 / 10 = 4
let remainder = divison % 3 // 4 % 3 = 1
```

### `Int8`

`Int8`s can store any number between -128 and 127.

```swift
let myInt8: Int8 = 100
```

Any number below -128 or above 127 is a compile-time error.

```swift
let tooLow: Int8 = -200
let tooHigh: Int8 = 200
```

Luckily you don't have to remenber those values. You can find those values by using `Int8.min` and `Int8.max`.

```swift
let minForAnInt8 = Int8.min
let maxForAnInt8 = Int8.max
```

But if you don't want use them, you can always use `-128` and `127`

```swift
let alsoMinForAnInt8: Int8 = -128
let alsoMaxForAnInt8: Int8 = 127
```


