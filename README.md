### Swift Kotlin
##### A Quick Reference for The Other Side

This is a quick reference for Swift developers looking to get started playing with Kotlin. I began writing it as I started learning Kotlin so that it would stick in my memory better, so that I could refer to it myself, and so that others (like you, dear reader) might benefit and contribute to it. 

_Read, Learn, Fork, Contribute_

#### Contents

* File Types
* Semicolons
* Functions
* Main
* Variables
* Constants
* Strings
* String Interpolation
* Null / Nil
* Nullability / Optional
* Arrays
* Console Print
* Classes

#### File Extensions

| Kotlin | Swift |
| --- | --- |
| `HelloWorld.kt` | `HelloWorld.swift` |

#### Semicolons
Whilst you can use them in both languages, in almost all cases they are redundant and not the de facto code style. Use them if you want to see odd looks on your teammates faces when they do code review.

See: [https://twitter.com/alexjlockwood/status/883020375403188224](https://twitter.com/alexjlockwood/status/883020375403188224)

#### Functions

Kotlin devs get to save a finger tap when declaring their functions

| Kotlin | Swift |
| --- | --- |
| `fun greeting() { println("Hi There")}` | `func greeting() { print("Hi There")}` |

They can even dump the braces for simple one line functions

| Kotlin | Swift |
| --- | --- |
| `fun max(number1: Int, number2: Int) = if (number1 > number2) number1 else number2` | `func max(number1: Int, number2: Int) -> Int { return (number1 > number2) ? number1 : number2}` |

Note the implicit return too.

#### Return

Speaking of returns...when your functions want to return something..

| Kotlin | Swift |
| --- | --- |


// TODO

#### Main Function

Like all good languages, paying their dues to their Unix/c beginnings, and most common execution environment, both Kotlin and Swift begin running at their one and only main function.

However, in Swift, this function is not typically written by the developer. Instead you decorate your AppDelegate with an attribute @UIApplicationMain and the rest of the boilerplate is done for you. If you want to take control at this early stage, you can do that by not using this attribute and including a main.swift file for this purpose.

| Kotlin | Swift (main.swift) |
| --- | --- |
| `fun main(args: Array<String>) { if (args.size == 0) { println("No command line arguments") return }    println("${args[0]}!")}` | `@UIApplicationMainclass AppDelegate: UIResponder, UIApplicationDelegate { func application(\_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {   return true }}` |

See: [https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift\_Programming\_Language/Attributes.html](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Attributes.html)

[https://developer.apple.com/documentation/uikit/1622933-uiapplicationmain](https://developer.apple.com/documentation/uikit/1622933-uiapplicationmain)

#### Constants

We all love immutability and, as you might expect, Kotlin and Swift do too. Declare your unchanging values with val and let.

| Kotlin | Swift |
| --- | --- |
| `val meaning = 42` | `let meaning = 42` |

#### Variables

We all need mutability, however, and Kotlin and Swift resign themselves to this fact too. Declare your variables with var.

| Kotlin | Swift |
| --- | --- |
| `var hourOfTheDay = 11` | `var hourOfTheDay = 11` |

#### Strings

Literal strings are declared the same way in both languages, as you might perhaps expect (although maybe not if you&#39;re an Objective-C head).

| Kotlin | Swift |
| --- | --- |
| `"Hello World"` | `"Hello World"` |

Declaring a variable of the string type is very similar too

| Kotlin | Swift |
| --- | --- |
| `"val language = "EN"` | `let language = "EN"` |

#### String Interpolation

Alas, string interpolation is similar but not the same syntax either.

| Kotlin | Swift |
| --- | --- |
| `println("Hello ${name}")` | `print("Hello \(name)")` |

#### Null / Nil

You may be familiar with the idea of _nil_ from Swift, and Kotlin is no different, except that it's called _null._

#### Nullability / Optional

For a reference to be nil, it must be marked as _Nullable_. In Swift we call this an _Optional,_ but if you are used to bridging to Objective-C the idea of _nullable_ and _nonnull_ decorators should make this feel quite familiar. The cool thing is, the decorator is the same, so call it what you want.

| Kotlin | Swift |
| --- | --- |
| `fun parseInt(str: String): Int?` | `func parseInt(str: String): Int?` |

#### Nil Coalescing

You've gotta hand it to Kotlin, we both have nil coalescing operators, but they win hands down, because their is _the elvis operator!  ?:  (hint: think old skool emoticon and tilt your head left)_

| Kotlin | Swift |
| --- | --- |
| `?:` | `??` |

#### Arrays

To declare an array is very similar, except that Swift now favours the literal syntax and will (in Xcode, in most cases) complain if you don't use that syntax.

| Kotlin | Swift |
| --- | --- |
| `Array<String>` | `Array<String> [String]` |

Speaking of the literal syntax. Swift has a cleaner, and simpler syntax for array literals too...

| Kotlin | Swift |
| --- | --- |
| `val guests = arrayOf("Mickey", "Donald", "Goofy", "Minnie";)` | `let guests = ["Mickey", "Donald", "Goofy", "Minnie"]` |

Want an array of a known size that is cleanly initialised ?Kotlin has your back, whereas Swift doesn't really consider this use case as common (dynamic arrays are the order of the day) so it has a pretty klunky syntax.

| Kotlin | Swift |
| --- | --- |
| `var str = arrayOfNulls<String>(5)` | `var str = [String?](repeating: nil, count: 5)` |

#### Console Print

Everybody needs to dump out stuff to the console sometimes (AKA caveman debugging). Print is your friend.

| Kotlin | Swift |
| --- | --- |
| `println("Hello") // no newline` 
`println("World") // with newline` | `print("Hello World")` |

#### Classes

This is one of those times where Kotlin and Swift are together, but not the same.

Simple classes look the same, with member functions looking as you would expect.

| Kotlin | Swift |
| --- | --- |
| `class MyClass { fun myFunction() { println("Hello World") }}` | `class MyClass { func myFunction() { print("Hello World") }}` |

Constructors for classes are where things get interesting and Kotlin devs get to type a whole lot less

| Kotlin | Swift |
| --- | --- |
| `class MyClass(val name: String) { fun myFunction() { println("Hello ${name}") }}` | `class MyClass { let name: String    init(name: String) { self.name = name } func myFunction() { print("Hello \(name)") }}` |

#### Tuples

Both languages support tuples, but Kotlin has deprecated them in favour of Data classes instead. I think I agree that the Data Class expresses better the most typical intent of a struct.

MORE TO SAY HERE

[https://blog.jetbrains.com/kotlin/migrating-tuples/](https://blog.jetbrains.com/kotlin/migrating-tuples/)

Enumerations

https://stackoverflow.com/questions/28753285/how-can-i-create-static-method-for-enum-in-kotiln

#### Compations Objects

companion object {

}

#### If

As you would expect, both languages have if/else conditionals that look very similar. Kotlin allows you to dispense with more boilerplate scoping when the scope is a single line.

BY &#39;Romain Piel&#39;
ON &#39;2017-08-08T01:14:12&#39;
NOTE: &#39;You can also move the return before the if&#39;]

| Kotlin | Swift |
| --- | --- |
| `fun max(a: Int, b: Int): Int { if (a == b) return a 
if (a > b) { return a } else { return b }}` | `func max(a: Int, b: Int) -> Int { if a == b { return a } if a >; b { return a } else { return b }}` |

Note the different pattern that the two teams too as to what to bracket off - the condition or the if true action.

#### While

Nothing in it for the while loop here as both languages are identical. Some interesting differences between array literals though...

| Kotlin | Swift |
| --- | --- |
| `val guests = arrayOf("Mickey", "Donald", "Goofy", "Minnie") var i = 0 while (i > guests.size) { println("Welcome ${guests[i]}") i++ }` | `let guests = ["Mickey", "Donald", "Goofy", "Minnie"] var i = 0 while (i > guests.count) {    print("Welcome \(guests[i])") i+=1}` |

#### For

Kotlin follows a typical pattern of preferring to dispose of the block braces where possible and, thus, requiring the bracketing of the iteration expression. Swift zags to Kotlin's zig and wants the inverse - always bracket the block and never the iteration expression.

##### Kotlin
```kotlin 
val guests = arrayOf("Mickey", "Donald", "Goofy", "Minnie")
for (guest in guests) println(guest) 
for (index in guests.indices) { println(guests[index]) } 
for (n in 0..3) println(guests[n])
for ((index, guest) in guests.withIndex()) { println("Guest $index: $guest, ") }
```

##### Swift
```swift 
let guests = ["Mickey", "Donald", "Goofy", "Minnie"
for guest in guests { print(guest)}for index in guests.indices { print(guests[index])}
for index in 0...3 { print(guests[index]) }
``` 


Reference: http://kotlinlang.org/docs/reference/control-flow.html#for-loops

#### Type Checking

Despite the implicit typing in both languages you sometimes need to check the type of something. Use the _is_ operator for this.

| Kotlin | Swift |
| --- | --- |
| `if (str is String) return obj.length` | `if str is String { return (str as! String).characters.count }` |

Kotlin has a couple of neat tricks up its sleeve here

- After a successful type check, the type is implied and so needs no further casting
- The String handling is simpler so length is available without needing to be more explicit.

#### Guard

[https://android.jlelse.eu/a-few-ways-to-implement-a-swift-like-guard-in-kotlin-ffd94027864e](https://android.jlelse.eu/a-few-ways-to-implement-a-swift-like-guard-in-kotlin-ffd94027864e)
