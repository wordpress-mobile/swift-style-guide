# Process to add a new rule

If you want to suggest an addition to the style guide, create a new issue. It
should include a good explanation, and examples of good/bad usage, unless the
difference is obvious (e.g. tabs vs spaces). It should include other
alternatives and an explanation of why this one is better, even if it’s just
“it’s the one most commonly used”. Ideally, the body of the issue should be good
enough to put in the style guide as-is if approved. Bonus points if the issue
contains a custom rule for SwiftLint.

Once an issue is created, we use Github reactions to gather interest. Issues
with more :+1: get reviewed first. See [proposals sorted by vote](https://github.com/wordpress-mobile/swift-style-guide/issues?q=is%3Aissue+is%3Aopen+label%3Aproposal+sort%3Areactions-%2B1-desc)

Anyone is free to leave a comment with their opinion at this point, or ask for clarifications, but there’s no review yet.

When it’s time for a review, one or more issues are picked (depending on their
expected controversy), and they’re up for review. Everyone is encouraged to take
a look at the reviewed issues, and leave their opinion and vote. To create a new
review, a Pull Request is created with the requested changes.

There should be a voting scale:

- :+1: :+1: I believe this is much better than the
alternative
- :+1: I prefer this one
- :neutral_face: I don’t care
- :-1: I prefer the alternative
- :-1: :-1: I think the alternative is much better

If you leave a vote in either end of the scale, it should come with a good
explanation.

When the review period is over, the votes and arguments are taken into account
and a decision is made. The new rule gets added to the guide and, if possible, a
new rule is added to the linter.
