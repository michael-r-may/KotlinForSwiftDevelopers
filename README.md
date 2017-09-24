#### Swift Kotlin
A Quick Reference for The Other Side

This is a quick reference for Swift developers looking to get started playing with Kotlin.

File Types

Semicolons

Functions

Main

Variables

Constants

Strings

String Interpolation

Null / Nil

Nullability / Optional

Arrays

Console Print

Classes

File Types

| Kotlin | Swift |
| --- | --- |
| HelloWorld.kt | HelloWorld.swift |

Semicolons

Whilst you can use them in both languages, in almost all cases they are redundant and not the de facto code style. Use them if you want to see odd looks on your teammates faces when they do code review.

See: [https://twitter.com/alexjlockwood/status/883020375403188224](https://twitter.com/alexjlockwood/status/883020375403188224)

Functions

Kotlin devs get to save a finger tap when declaring their functions

| Kotlin | Swift |
| --- | --- |
| fun greeting() {      println(&quot;Hi There&quot;)} | func greeting() {      print(&quot;Hi There&quot;)} |

They can even dump the braces for simple one line functions

| Kotlin | Swift |
| --- | --- |
| fun max(number1: Int, number2: Int) = if (number1 &gt; number2) number1 else number2 | func max(number1: Int, number2: Int) -&gt; Int {    return (number1 &gt; number2) ? number1 : number2} |

Note the implicit return too.

Return

When your functions want to return something..

// TODO

Main Function

Like all good languages, paying their dues to their Unix/c beginnings, and most common execution environment

# 1
, both Kotlin and Swift begin execution at their one and only main function.

However, in Swift, this function is not typically written by the developer. Instead you decorate your AppDelegate with an attribute @UIApplicationMain and the rest of the boilerplate is done for you. If you want to take control at this early stage, you can do that by not using this attribute and including a main.swift file for this purpose.

| Kotlin | Swift (main.swift) |
| --- | --- |
| fun main(args: Array&lt;String&gt;) {    if (args.size == 0) {        println(&quot;No command line arguments&quot;)        return    }    println(&quot;${args[0]}!&quot;)} | @UIApplicationMainclass AppDelegate: UIResponder, UIApplicationDelegate {    func application(\_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -&gt; Bool {        return true    }} |

See: [https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift\_Programming\_Language/Attributes.html](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Attributes.html)

[https://developer.apple.com/documentation/uikit/1622933-uiapplicationmain](https://developer.apple.com/documentation/uikit/1622933-uiapplicationmain)

Constants

We all love immutability and, as you might expect, Kotlin and Swift do too. Declare your unchanging values with val and let.

| Kotlin | Swift |
| --- | --- |
| val meaning = 42 | let meaning = 42 |

Variables

We all need mutability, however, and Kotlin and Swift resign themselves to this fact too. Declare your variables with var.

| Kotlin | Swift |
| --- | --- |
| var hourOfTheDay = 11 | var hourOfTheDay = 11 |

Strings

Literal strings are declared the same way in both languages, as you might perhaps expect (although maybe not if you&#39;re an Objective-C head).

| Kotlin | Swift |
| --- | --- |
| &quot;Hello World&quot; | &quot;Hello World&quot; |

Declaring a variable of the string type is very similar too

| Kotlin | Swift |
| --- | --- |
| val language = &quot;EN&quot; | let language = &quot;EN&quot; |

String Interpolation

Alas, string interpolation is similar but not the same syntax either.

| Kotlin | Swift |
| --- | --- |
| println(&quot;Hello ${name}&quot;) | print(&quot;Hello \(name)&quot;) |

Null / Nil

You may be familiar with the idea of _nil_ from Swift, and Kotlin is no different, except that it&#39;s called _null._

Nullability / Optional

For a reference to be nil, it must be marked as _Nullable_. In Swift we call this an _Optional,_ but if you are used to bridging to Objective-C the idea of _nullable_ and _nonnull_ decorators should make this feel quite familiar. The cool thing is, the decorator is the same, so call it what you want.

| Kotlin | Swift |
| --- | --- |
| fun parseInt(str: String): Int? | func parseInt(str: String): Int? |

Nil Coalescing

You&#39;ve gotta hand it to Kotlin, we both have nil coalescing operators, but they win hands down, because their is _the elvis operator!  ?:  (hint: think old skool emoticon)_

| Kotlin | Swift |
| --- | --- |
| ?: | ?? |

Arrays

To declare an array is very similar, except that Swift now favours the literal syntax and will (in Xcode, in most cases) complain if you don&#39;t use that syntax.

| Kotlin | Swift |
| --- | --- |
| Array&lt;String&gt; | Array&lt;String&gt; [String] |

Speaking of the literal syntax. Swift has a cleaner, and simpler syntax for array literals too...

| Kotlin | Swift |
| --- | --- |
|   val guests = arrayOf(&quot;Mickey&quot;, &quot;Donald&quot;, &quot;Goofy&quot;, &quot;Minnie&quot;) | let guests = [&quot;Mickey&quot;, &quot;Donald&quot;, &quot;Goofy&quot;, &quot;Minnie&quot;] |

Console Print

Everybody needs to dump out stuff to the console sometimes (AKA caveman debugging). Print if your friend.

| Kotlin | Swift |
| --- | --- |
| println(&quot;Hello &quot;) // no newlineprintln(&quot;World&quot;) // with newline | print(&quot;Hello World&quot;) |

Classes

This is one of those times where Kotlin and Swift are together, but not the same.

Simple classes look the same, with member functions looking as you would expect.

| Kotlin | Swift |
| --- | --- |
| class MyClass {    fun myFunction() {        println(&quot;Hello World&quot;)    }} | class MyClass {    func myFunction() {        print(&quot;Hello World&quot;)    }} |

Constructors for classes are where things get interesting and Kotlin devs get to type a whole lot less

| Kotlin | Swift |
| --- | --- |
| class MyClass(val name: String) {    fun myFunction() {        println(&quot;Hello ${name}&quot;)    }} | class MyClass {    let name: String    init(name: String) {      self.name = name       }    func myFunction() {        print(&quot;Hello \(name)&quot;)    }} |

Tuples

Both languages support tuples, but Kotlin has deprecated them in favour of Data classes instead. I think I agree that they are not needed.

MORE TO SAY HERE

[https://blog.jetbrains.com/kotlin/migrating-tuples/](https://blog.jetbrains.com/kotlin/migrating-tuples/)

Enumerations

https://stackoverflow.com/questions/28753285/how-can-i-create-static-method-for-enum-in-kotiln

companion object {

}

If

As you would expect, both languages have if/else conditionals that look very similar. Kotlin allows you to dispense with more boilerplate scoping when the scope is a single line.

| Kotlin | Swift |
| --- | --- |
| fun max(a: Int, b: Int): Int {    if (a == b) return a

#
[ANNOTATION:

BY &#39;Romain Piel&#39;
ON &#39;2017-08-08T01:14:12&#39;
NOTE: &#39;You can also move the return before the if&#39;]
if (a &gt; b) {
        return a    } else {        return b    }} | func max(a: Int, b: Int) -&gt; Int {    if a == b { return a }        if a &gt; b {        return a    } else {        return b    }} |

Note the different pattern that the two teams too as to what to bracket off - the condition or the if true action.

While

Nothing in it for the while loop here as both languages are identical. Some interesting differences between array literals though...

| Kotlin | Swift |
| --- | --- |
|   val guests = arrayOf(&quot;Mickey&quot;, &quot;Donald&quot;, &quot;Goofy&quot;, &quot;Minnie&quot;)        var i = 0    while (i &lt; guests.size) {            println(&quot;Welcome ${guests[i]}&quot;)            i++        } | let guests = [&quot;Mickey&quot;, &quot;Donald&quot;, &quot;Goofy&quot;, &quot;Minnie&quot;]var i = 0while (i &lt; guests.count) {    print(&quot;Welcome \(guests[i])&quot;)    i+=1} |

For

Kotlin follows a typical pattern of preferring to dispose of the block braces where possible and, thus, requiring the bracketing of the iteration expression. Swift zags to Kotlin&#39;s zig and wants the inverse - always bracket the block and never the iteration expression.

| Kotlin | Swift |
| --- | --- |
|     val guests = arrayOf(&quot;Mickey&quot;, &quot;Donald&quot;, &quot;Goofy&quot;, &quot;Minnie&quot;)        for (guest in guests)        println(guest)    for (index in guests.indices) {        println(guests[index])    }        for (n in 0..3) println(guests[n]) | let guests = [&quot;Mickey&quot;, &quot;Donald&quot;, &quot;Goofy&quot;, &quot;Minnie&quot;]for guest in guests {    print(guest)}for index in guests.indices {    print(guests[index])}for index in 0...3 { print(guests[index]) } |

Reference: http://kotlinlang.org/docs/reference/control-flow.html#for-loops

Type Checking

Despite the implicit typing in both languages you sometimes need to check the type of something. Use the _is_ operator for this.

| Kotlin | Swift |
| --- | --- |
| if (str is String) return obj.length | if str is String { return (str as! String).characters.count } |

Kotlin has a couple of neat tricks up its sleeve here

- After a successful type check, the type is implied and so needs no further casting
- The String handling is simpler so length is available without needing to be more explicit.

Guard

[https://android.jlelse.eu/a-few-ways-to-implement-a-swift-like-guard-in-kotlin-ffd94027864e](https://android.jlelse.eu/a-few-ways-to-implement-a-swift-like-guard-in-kotlin-ffd94027864e)