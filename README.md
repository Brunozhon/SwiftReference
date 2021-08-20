# Swift 5.3 Reference

A Swift 5.3 reference including code examples.

## How to use

There are no `.zip` or `.tar.gz` files to manage. Simply read this reference online and you're done!

## Want to contribute?

- Suggest code examples by creating an [Issue](https://github.com/Brunozhon/SwiftReference/issues/new/choose) or [creating a Discussion](https://github.com/Brunozhon/SwiftReference/discussions/new).
- Add your own code examples by [creating a Pull Request](https://github.com/Brunozhon/SwiftReference/compare).

For more information, check out [CONTRIBUTING.md](https://github.com/Brunozhon/SwiftReference/blob/main/CONTRIBUTING.md#contributing).

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
- [Variables](#variables)
  - [`var`](#var)
  - [`let`](#let)
- [Functions and Closures](#functions-and-closures)
  - [Functions](#functions)
    - [Async and Await](#async-and-await)
    - [Mutating](#mutating)
    - [Return Types](#return-types)
  - [Closures](#closures)
- [Conditionals and Loops](#statements-and-loops)
  - [If](#if)
  - [If-else](#if-else)
  - [If-else if-else](#if-else-if-else)
  - [For](#for)
  - [While](#while)
  - [Repeat-while](#repeat-while)
- [Structures and Enumrations](#structures-and-enumrations)
  - [Structures](#structures)
    - [Methods](#methods)
    - [Properties](#properties)
    - [Initlizers](#initlizers)
  - [Enumarations](#enumarations)
    - [Associated Values](#associated-values)



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
> 3.14159
> 9.99999
> 0.00001
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

What was the most intresting topic? (This list in uncheckable, but you can pretend you are checking the option. Or you can write the list yourself and tick the topic that you think was most intresting.)

- [ ] Strings
- [ ] Integers
- [ ] Unsigned Integers
- [ ] Doubles
- [ ] Floats
- [ ] Booleans
- [ ] None

## Variables

There are two diffrent types of variables. They are `var` and `let`.

You can define a variable like this (for var):

```swift
var name = value
var name: type = value
var name: type // NEW!
```

And this (for let):

```swift
let name = value
let name: type = value
```

### `var`

`var` defines a variable.

```swift
var myFavoriteNumber = 10
```

You can use it for storing your favorite `UIKit` color.

```swift
import UIKit
var myFavoriteColor = UIColor.red
```
### `let`

`let` defines a constant.

```swift
let myName = "John Doe"
```

## Functions and Closures

A function is declared like this:

```swift
func functionName(parameterName: ParameterType) {
  code
}
```

Or this:

```swift
func functionName(parameterName: ParameterType) -> ReturnType {
  code
}
```

A closure is declared like this:

```swift
{ (parameterName: ParameterType) -> ReturnType in
  code
}
```

> **Why capitalize the first letter?**
> Swift developers capitalize names of types to avoid confusion between types and variables. This is useful if you had a structure/class with the same name as a variable. Like this:
> ```swift
> class Space { /*...*/ }
> var space = Space()
> ```
> Or you would end up with this:
> ```swift
> class space { /*...*/ }
> var mySpace = space()
> ```
> And you would have to rename the variable. And you will not be happy. Especially if you wanted to name your variable `space`.

### Functions

Imagine repeating this block of code many times.

```swift
person.moveForward()
person.turnLeft()
person.moveForward()
person.shakeHands(with: anotherPerson)
person.uTurn()
person.moveForward()
person.turnLeft()
```

You can make a function. Like this:

```swift
func shakeHandsWithAPerson() {
  person.moveForward()
  person.turnLeft()
  person.moveForward()
  person.shakeHands(with: anotherPerson)
  person.uTurn()
  person.moveForward()
  person.turnLeft()
}
```

Or one with parameters:

```swift
func shakeHands(with: Person) {
  person.moveForward()
  person.turnLeft()
  person.moveForward()
  person.shakeHands(with: with)
  person.uTurn()
  person.moveForward()
  person.turnLeft()
}
```

But if you don't want to use `with` as a parameter name in the function, you could use this syntax for a function:

```swift
func functionName(parameterLabel parameterName: ParameterType) {

}
```

Which solves the problem like this:

```swift
func shakeHands(with: Person) {
  person.moveForward()
  person.turnLeft()
  person.moveForward()
  person.shakeHands(with: anotherPerson)
  person.uTurn()
  person.moveForward()
  person.turnLeft()
}
```

#### `async` and `await`

Asynchronous functions are defined like this:

```swift
func fetchJSON(fromServer server: String) async -> [String: String] {
  let fetchedJSON = await MyDataFetcher.fetch(fromServer: server)
  let decodedSwiftDictionary: [String: String] = MyDecoder.decodeJSON(fetchedJSON.body)
  return decodedSwiftDictionary
}
```

You can use it like this:

```swift
let exampleUser = await fetchJSON(fromServer: "https://api.example.com/users/myUsername")
```

MyDecoder is going to convert the body of the HTTP response into a Swift dictionary.

So assume the header is this:

```
200 OK
Content-Type: application/json
...
X-Sessions-Left: 59
```

And the body is this:

```json
{
  "username":"myUsername",
  "name":"My Username",
  "projects":[
    {
      "name":"My Project",
      "contents":[
         "index.html",
         "img/blah.png",
         "404.html"
      ],
      "website_project":"true"
    }
  ]
}
```

MyDecoder is going to decode it into this:

```swift
[
  "username":"myUsername",
  "name":"My Username"
]
```

But why? Swift is a **type-safe language**, so you can't assign a value that is supposed to be `String` into an `Int`.

#### Mutating

Mutating functions can be declared in a struct or a enum.

```swift
struct MyStruct {
  var myVariable = 100
  mutating func add100() {
    myVariable += 100
  }
}
enum MyEnum {
  case myCase
  case anotherCase
  mutating func changeCases() {
    switch self {
      case .myCase:
        self = .anotherCase
      case .anotherCase:
        self = .myCase
    }
  }
}
```

They can mutate a variable.

#### Return Types

You define a return type using an arrow `->` and the return type. Easy, peasy.

```swift
func return15() -> Int {
  return 15
}
```

But the function has to return the value, otherwise it is a compile time error. 

### Closures

You can store a closure like this:

```swift
let greet = { (person: Person) -> Void in
  print("Hello \(person.name)!")
}
```

Wait &mdash; what is `Void`?

> **Quick reference:**
> `Void` is an empty tuple. So what are tuples? 
> > **Quick reference:**
> > A tuple can be declared like this:
> > ```swift
> > let toy = ("Toy Train", 5.99)
> > ```
> > You can access the properties like this:
> > ```swift
> > let toyName = toy.0
> > ```
> > You can decompose a tuple like this:
> > ```swift
> > let (name, price) = toy
> > ```
> > When you need just a value, you can skip unwanted values with an underscore.
> > ```swift
> > let (_, justThePrice) = toy
> > let(justTheName,_) = toy
> > ```
> So `Void` is a subsitute for this:
> ```swift
> ()
> ```

Closures can return a value. But it has to be other than `Void`.

```swift
let return150 = { (number: Int) -> Int in
  return 150
}
```

Later, you can call it.

```swift
return150()
```

So, closures are easy as pie.

## Statements and Loops

### If

If has a simple syntax.

```swift
if condition {
  code
}
```

You can use an if conditional like this:

```swift
let isMember = false
if isMember {
  print("Welcome!")
}
```

You can combine booleans with the _logical and operator_ (`&&`) or the _logical or operator_ (`||`).

```swift
let passedFingerprintTest = false
if isMember && passedFingerprintTest {
  print("Welcome!")
}
```

```swift
let knowsPassword = true
let passedFaceIDScan = true
if isMember && passedFingerprintTest || knowsPassword && passedFaceIDScan {
  print("Welcome!")
}
```

### If-else

If-else conditionals also have a simple syntax:

```swift
if condition {
  code
} else {
  code
}
```

You can use them like this:

```swift
var password = "myPassword123"
if password == "myPassword123" {
  print("Welcome My User!")
} else {
  print("Wrong password: \(password)")
}
```

Or this:

```swift
var username = "myPassword123sUser"
var faceIDScan = "ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ"
if password == "myPassword123" && username == "myUser123" && faceIDScan = "ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ" {
  print("Welcome My User!")
} else {
  print("Wrong username \(username), password \(password), or face ID scan \(faceIDScan)")
}
```

### If-else if-else

If-else if-else conditonals have a simple syntax.

```swift
if condition {
  code
} else if anotherCondition {
  code
} else {
  code
}
```

You can use it like this:

```swift
let num = 3
if num < 3 {
  print("num is less than three")
} else if num == 3 {
  print("num is three")
} else {
  print("num is greater than three")
}
```

If you want, you can omit the `else`.

```swift
if num < 3 {
  print("num is less than three")
} else if num > 3 {
  print("num is greater than three")
}
```

### Switches

A switch is defined like this:

```swift
switch variableName {
  case caseOne:
    code
  case caseTwo, caseThree:
    code
  default:
    code
}
```

Switches have to be exhaustive. That means you must handle every possible value in a switch like this:

```swift
var favoriteVegtable = "tomato"
switch favoriteVegtable {
  case "tomato":
    print("Make tomato soup.")
  case "lettuce", "cabbage", "cucumber", "kale":
    print("Make salad.")
  case "celery":
    print("Make ants on a log.")
  default:
    print("No suggestion.")
}
```

Switches must have at least one executable statement. If you don't have one, you can use `break`:

```swift
break
```

### For

For loops have a simple syntax:

```swift
for i in 1...number {
  code
}
```

You can use `break` and `continue` in a for loop.

`break` breaks out of the loop.

```swift
for i in 1...100 {
  if i == 50 {
    break
  }
  print(i, terminator: " ")
}
```

`continue` skips the iteration.

```swift
for i in 1...10 {
  if !i.isMultiple(of: 2) {
    continue
  }
  print(i, terminator: " ")
}
```

If you don't want every value, you can use `stride(from:to:by:)`.

```swift
for i in stride(from: 1, to: 10, by: 2) {
  print(i, terminator: " ")
}
```

The *range operator* (`...`) is what I've been using in the code samples. If you don't want to include the final number, you can use the *half-open range operator* (`..<`).

```swift
for i in 1..<10 {
  print(i, terminator: " ")
}
```

### While

While loops look like this:

```swift
while condition {
  code
}
```

A while loop that looks like this:

```swift
var i = 5
while i != 0 {
  print("\(i)...")
  i -= 1
}
print("Blast off!")
```

It will print:

```
5...
4...
3...
2...
1...
Blast off!
```

### Repeat-while

`repeat-while` loops run once, then evaluate the condition. If it is true, it keeps going. Like this:

```swift
var x = 2
print("\(x)...")
repeat {
  x *= 2
  print("\(x)...")
} while x > 100
x *= 2
print("\(x)!")
```

It will print:

```
2...
4...
8...
16...
32...
64...
128...
256!
```

## Structures and Enumrations

### Structures

A structure is defined like this:

```swift
struct StructName {
  fields
}
```

A structure declaration can contain:

- Methods
- Properties
- Initlizers

#### Methods

Methods are like functions. But they're in a structure. Here's an example:

```swift
struct Counter {
  ...
  func getValue() {
    return x
  }
  ...
}
```

Remenber [mutating functions](#mutating)? They can change a value, like this:

```swift
struct Counter {
  ...
  mutating func add() {
    x += 1
  }
  mutating func add(_ amount: Int) {
    x += amount
  }
  ...
}
```

#### Properties

Properties are like variables but they're in a structure.

```swift
struct Counter {
  var x: Int
  ...
}
```

Easy peasy.

#### Initlizers

Initlizers intilize structures. Like this:

```swift
struct Counter {
  ...
  init(startsFrom value: Int) {
    x = value
  }
  ...
}
```

Later you can use it:

```swift
var myCounter = Counter(startsFrom: 1)
```

You can access properties and methods afterwards:

```swift
myCounter.x // 1
myCounter.getValue() // also 1
myCounter.add() // 2
myCounter.add(10) // 12
```

**Did you know?** Structures gain a default initlizer if no initlizer was specifed. So you could initlize a structure like this:

```swift
Counter(x: 1, ...)
```

### Enumarations


Enumarations are declared like this:

```swift
enum EnumName {
  case caseName
}
```

Enumarations can have more than one case:

```swift
enum Fruit {
  case apple
  case banana
  case orange
  case grape
  case strawberry
  case blueberry
  case rasberry
}
```

You can initlize a enum like this:

```swift
var myFavoriteFruit = Fruit.banana
```

After that, you can use a shortened form like this:

```swift
myFavoriteFruit = .rasberry
```

#### Associated Values

Associated values are written like this:

```swift
enum EnumName {
  case caseName(AssociatedTypeOne, AssociatedTypeTwo)
  case anotherCase(associatedTypeNameOne: AssociatedTypeOne, associatedTypeNameTwo: AssociatedTypeTwo)
}
```

Just like this:

```swift
enum Projectile {
  case sword(damage: Int, enchantements: [Enchantment])
  case shield(damageProtectedFromPlayer: Int, enchantments: [Enchantment])
  case armor(damageProtectedFromPlayer: Int, heaviness: Int, enchantements: [Enchantment])
  case potion(effect: Enchantment, fullness: Percent, type: PotionType)
}
```

You can initlize a enum with cases with associated values like this:

```swift
var myProjectile = Projectile.sword(damage: Int, enchantments: [.doubleTheDamage, .weakness(100)])
```

You can change it like this:

```swift
myProjectile = .potion(effect: .weakness(100), fullness: Percent(100), type: .splashPotion)
```

So why group structures and enumarations together?

<details>
  <summary>Answer</summary>
  <p>Because they're <b>value types</b>.</p>
</details>
