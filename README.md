# The Swift Style Guide for Wordpress Mobile apps

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
