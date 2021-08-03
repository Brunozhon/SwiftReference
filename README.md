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

There are several of types in Swift. They are:

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
