# The Swift Style Guide for WordPress Mobile apps

So you want to write some Swift code for WordPress apps. That’s nice, thanks a
lot. But before that take some minutes to read some tips that will probably make
everyone’s life easier.

First, read the [Swift API Design
Guidelines](https://swift.org/documentation/api-design-guidelines/) carefully.
It’s not a long document and it establishes a common ground for what good Swift
code looks like.

Our approach to building a style guide is to do it incrementally and reach
consensus. You can read more about the [process](PROCESS.md).

When there is not a rule for something or there’s ambiguity, you’re encouraged
to create a new issue with a proposal. In the meantime, the [raywenderlich.com
Swift Style Guide](https://github.com/raywenderlich/swift-style-guide/) is often
a good place to look for reference, but it’s not our official guide.

Besides keeping this document short, we’re trying to organize it in two
sections: a _must read_ section for rules we can’t automatically enforce, and an
_all rules_ section as a reference of every other approved rule. You are not
required to read the _all rules_ section, as Xcode will tell you when you break
those rules.

## Must read

### Fix all the warnings

We’re using [SwiftLint](https://github.com/realm/SwiftLint) to enforce as many
of our rules as we can, so trust the warnings. Don’t commit or merge code with
warnings. Our `Release` builds turn warnings into errors, so if you merge a
warning you will create a problem for the person doing the release later on.

### Deal with optionals early

Don't allow optional parameters just to return when they're `nil`.

```swift
// Correct: the return value has a chance to become non-optional.  Reduced complexity.
func process(image: UIImage) -> UIImage {
    // ...process the image...
}
let processedImage = optionalImage.map(process)

// Wrong: the return value becomes an optional as well.  Added complexity.
func process(image: UIImage?) -> UIImage? {
    guard let image == image else {
        return nil
    }

    // ...process the image...
}
let processedImage = process(optionalImage)
```

## All the rules

### Trailing new line

Files should end in **one** empty new line. A missing new line at the end causes
trouble with diffs when the last line changes. More than one empty line is
unnecessary.

### Avoid trailing whitespace

There’s no need for whitespace at the end of lines and it is often the cause for
unnecessary noise in diffs.

You can go to Xcode’s preferences for _Text Editing_ and make sure both
_Automatically trim trailing whitespace_ and _Including whitespace-only lines
are enabled_. Xcode misses some cases, but it should help a lot.

### Avoid semicolons

Swift does not require a semicolon after each statement in your code. There’s no
reason to add them.

### Colon spacing

Colons always have no space on the left and one space on the right when
specifying a type.

```swift
// Correct
let name: String
struct MyType: MyProtocol {}
func prompt<T: UIViewController>(t: T) where T: Confirmable {}

// Wrong
let name : String
struct MyType : MyProtocol {}
func prompt<T : UIViewController>(t: T) where T : Confirmable {}
```

### Braces

Opening braces should be preceded by a single space and on the same line as the declaration. The exception to this rule is when enclosed within parentheses: no preceding space is required.

``` swift
// Correct
if let myString = myString {
    print(myString)
}

struct Foo {
    let bar: String
}

foo.map({ print($0) })

// Wrong
if let myString = myString
{
    print(myString)
}

struct Foo
{
    let bar: String
}
```

Closing braces should always be placed on a new line regardless of the number of enclosed statements.

```swift
// Correct
guard condition else {
   return
}

// Correct
if condition { 

} else {

}

// Wrong
guard condition else { return }

// Wrong
if condition { } else { }
```

### Commas

There should be no space before a comma and a single one after any comma.

**Preferred:**
```swift
function print(name: String, surname: String) {
  ...
}
```

**Not Preferred:**
```swift
function print(name: String ,surname: String) {
  ...
}
```

## Parentheses

Parentheses around conditionals, if, for, while, do statements, are not required and should be omitted.

**Preferred:**
```swift
if name == "Hello" {
  print("World")
}
```

**Not Preferred:**
```swift
if (name == "Hello") {
  print("World")
}
```

### Forced downcasts and unwrapping

Avoid using `as!` to force a downcast, or `!` to force unwrapping. Use `as?` to attempt the cast, then deal with the failure case explicitly.

``` swift
// Correct
func process(someObject: Any) {
    guard let element = someObject as? Element else {
        // Optional error handling goes here
        return
    }
    process(element)
}

// Wrong
func process(someObject: Any) {
    process(someObject as! Element)
}
```
