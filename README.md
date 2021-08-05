# Swift Reference

## Table of Contents

- [Types](#types)
  - [Strings](#strings)
  - [Integers](#integers)
    - [Int8](#int8)
    - [Int16](#int16)
    - [Int32](#int32)
    - [Int64](#int64)
  - [Unsigned Integers](#unsigned-integers)
  - [Doubles](#doubles)
  - [Floats](#floats)


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
  - `UInt32` (On a 32-bit platform, `UInt` is equal to `UInt32`)
  - `UInt64` (On a 64-bit platform, `UInt` is equal to `UInt64`)
- `Double`
- `Float`
- `Bool`

### Strings

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

#### `Int8`

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

#### `Int16`

`Int16`s can store any number between -32,768 and 32,767. Useful if `Int8`s don't have enough space.

```swift
let twoThousand: Int16 = 2000
```

But you can still use `Int8`s if you want.

```swift
let twentyTwo: Int8 = 22
```

When you add them, you have to do type conversion.

```swift
let twoThousandTwentyTwo = twoThousand + Int16(twentyTwo)
```

You will also get a compile-time error if you give it a value lower than -32768 and higher than 32767.

```swift
let tooLow: Int16 = -50000
let tooHigh: Int16 = 50000
```

You can also use `Int16.min` and `Int16.max`.

```swift
Int16.min
Int16.max
```

#### `Int32`

> **Quick reference:**
> You can format numbers using underscores. I will be using this method later on.

`Int32`s can store from -2,147,483,648 to 2,147,483,647. That's a lot!

```swift
let twoBillion: Int32 = 2_000_000_000
```

You will need to type convert when adding other values.

```swift
let twoBillionTwoThousandTwentyTwo: Int32 = twoBillion + Int32(twoThousand) + Int32(twentyTwo)
```

And you will get a compile-time error if you set it lower than -2,147,483,648 or higher than 2,147,483,647.

```swift
let tooLow: Int32 = -2_500_000_000
let tooHigh: Int32 = 2_500_000_000
```

And you can also use `Int32.min` and `Int32.max`.

```swift
Int32.min
Int32.max
```

> **Note:**
> `Int32` is `Int` on 32-bit platforms. So you can do this:
> ```swift
> let anInt32 = 2_000_000
> ```
> instead of this:
> ```swift
> let anInt32: Int32 = 2_000_000
> ```

#### `Int64`

`Int64`s can store any number from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807! And you thought the range from `Int32.min` to `Int32.max` was a lot!

```swift
let anInt64: Int64 = 5_000_000_000_000 // 5 trillion
```

Also, you need to type convert when adding other values (not shown). And you will get a compile-time error if you set it to a number too big or too small. **Note:** Those numbers can be up to quintrillions (10 to the power of 18)!

```swift
let tooSmall: Int64 = -10_000_000_000_000_000_000 // minus 10 quintrillion
let tooBig: Int64 = 10_000_000_000_000_000_000 // 10 quintrillion
```

> **Note:**
> `Int64` is `Int` in 64-bit platforms. So you could use this code:
> ```swift
> let anInt64 = 5_000_000_000_000 // 5 trillion
> ```
> instead of this:
> ```swift
> let anInt64: Int64 = 5_000_000_000_000 // 5 trillion
> ```

### Unsigned Integers

Unsigned integers cannot have a minus sign (`-`).

They are declared with the type `UInt`.

```swift
let goodUnsignedInteger: UInt = 100
let badUnsignedInteger: UInt = -100
```

As you might know, `UInt`s have 4 types.

- `UInt8`
- `UInt16`
- `UInt32`
- `UInt64`

But you know a lot about integers (`Int8`, `Int16`, `Int32`, and `Int64` but not `Int`), so I will tell you a brief reference.

Anyways, you should go well with the table.

| `UInt` type | Min | Max                        |
|-------------|-----|----------------------------|
| `UInt8`     | 0   | 255                        |
| `UInt16`    | 0   | 65,535                     |
| `UInt32`    | 0   | 4,294,967,295              |
| `UInt64`    | 0   | 18,446,744,073,709,551,615 |

> **Additional notes:**
> `UInt32` is `UInt` in 32-bit platforms. `UInt64` is `UInt` in 64-bit platforms.
> So this code:
> ```swift
> let myUInt32: UInt32 = 4_000_000_000 // 4 trillion
> let myUInt64: UInt64 = 18_000_000_000_000_000_000 // 18 quintrillion
> ```
> can be replaced like this in 32-bit platforms:
> ```swift
> let myUInt32: UInt = 4_000_000_000 // 4 trillion
> let myUInt64: UInt64 = 18_000_000_000_000_000_000 // 18 quintrillion
> ```
> and this in 64-bit platforms:
> ```swift
> let myUInt32: UInt32 = 4_000_000_000 // 4 trillion
> let myUInt64: UInt = 18_000_000_000_000_000_000 // 18 quintrillion
> ```

### Doubles

Doubles are floating-point numbers.

> **What is a floating-point number?**
> A floating-point number is a decimal number. Remenber decimal numbers in math? They are numbers like this:
> ```swift
> 3.1419
> 9.9999
> 0.0001
> ```
> See? They all have a floating point. What is a floating point?
> A floating point is a decimal point. This is a decimal point (in case you forgot):
> ```
> .
> ```

They have precision of 15 decimal digits.

```swift
// Precise:
9.9999999999
// Not so precise:
9.99999999999999999999
```

They can be stored in a variable like this:

```swift
let myDouble = 3.1419
```

### Floats

Floats are just like doubles, but they have precision of 6 decimal digits and they have to be declared explictly, like this:

```swift
let myFloat: Float = 2.99
let stillADouble = 2.99
```

Floats are not so intresting, so how about some booleans?

### Booleans

Booleans can only be `true` or `false`, but they are very useful. They can be directly stored:

```swift
let myBoolean = true
```

or used in if loops.

> **Note:**
> You may not have learned about if loops, but we will learn them later.

```swift
if myBoolean {
  print("myBoolean is true!")
}
if myBoolean {
  print("Yay!")
} else {
  print("Boo!")
}
```

What was the most intresting topic?

- [ ] Strings
- [ ] Integers
- [ ] Unsigned Integers
- [ ] Doubles
- [ ] Floats
- [ ] Booleans
