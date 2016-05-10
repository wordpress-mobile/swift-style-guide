<!-- Add a description of the proposed rule, for instance:

Colons always have no space on the left and one space on the right when specifying a type.

-->

### Examples

<!--
Add some correct and wrong cases to clarify the rule. For instance:

```swift
// Correct
let name: String
struct MyType: MyProtocol {}
func prompt<T: UIViewController where T: Confirmable>(t: T) {}

// Wrong
let name : String
struct MyType : MyProtocol {}
func prompt<T : UIViewController where T : Confirmable>(t: T) {}
```
-->

### Rationale

<!--
If there's an objective reason why this is better than the alternative, explain it here. Or at least provide references to usage in the community (stdlib, blog posts, other style guides).

For instance:

[Swift Colon Care: High Fiber usage](http://ericasadun.com/2016/03/25/swift-colon-care-high-fiber-usage/) details the rationale and alternatives pretty well.

> This approach is consistent, prioritizes the role of the left item, and is (in > my opinion) quite readable.

While the stdlib uses _a space on both sides of the colon when it’s used for declaration or extension_, Apple Developer publications _always write colons with no space on the left (except ternary)_.
-->

### Enforcing the rule

<!--
If you know a good way to enforce this rule, add the information here. For instance:

SwiftLint includes a `colon` rule that implements this.
-->
