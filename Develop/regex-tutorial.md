# Regex Tutorial: Matching an Email

This tutorial explains how to create a regular expression pattern to match an email address. The pattern will match the username, domain name, and domain suffix of an email address. The tutorial will provide examples of valid and invalid email addresses that match the pattern.

## Summary

Suppose you need to validate email addresses in a web form or application. In that case, you can use a regular expression (regex) pattern to match the email address format and ensure that it meets the required criteria. This tutorial will guide you through creating a regex pattern to match an email address and explain each component of the pattern. 

The regex for matching an email address is:

regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Examples](#examples)
- [Author](#author)

## Regex Components

### Anchors
Anchors are used to assert position within a string. The `^` anchor asserts the position at the start of the string, and the `$` anchor asserts the position at the end.

- `^`: Asserts position at the start of the string.
- `$`: Asserts position at the end of the string.

### Quantifiers
Quantifiers specify the number of occurrences of a character.

- `+`: Matches 1 or more of the preceding token.
- `{2,6}`: Matches between 2 and 6 occurrences of the preceding token.

### OR Operator
The OR operator (`|`) allows for matching either the expression before or the expression after the operator.

### Character Classes
Character classes match any character within the specified set.

- `[a-z0-9_\.-]`: Matches any lowercase letter, digit, underscore, dot, or hyphen.
- `[\da-z\.-]`: Matches any digit, lowercase letter, dot, or hyphen.

### Flags
Flags are optional parameters that change how the regex engine matches the pattern.

`i`: Case-insensitive matching
`g`: Global search
`m`: Multiline search

In the context of email matching, flags are typically not used as the pattern is case-sensitive and designed to match a single occurrence.

### Grouping and Capturing
Grouping constructs are used to group multiple tokens together and create capture groups.

- `([a-z0-9_\.-]+)`: Captures the username part of the email.
- `([\da-z\.-]+)`: Captures the domain name.
- `([a-z\.]{2,6})`: Captures the domain suffix.

### Bracket Expressions
Bracket expressions match a single character contained within the brackets.

- `[a-z0-9_\.-]`: Matches any lowercase letter, digit, underscore, dot, or hyphen.
- `[a-z\.]{2,6}`: Matches any lowercase letter or dot, between 2 and 6 times.

### Greedy and Lazy Match
Greedy quantifiers match as many occurrences as possible, while lazy quantifiers match as few as possible.

### Boundaries
Boundaries match positions within the string, such as word boundaries. 

`\b`: Matches a word boundary.
`\B`: Matches a non-word boundary.

Boundaries are not specifically used in this email regex.

### Back-references
Back-references match the same text as previously matched by a capturing group.

Example (not applicable for email regex):

`(foo)\1`: Matches `foofoo`

Back-references are not used in this email regex.

### Look-ahead and Look-behind
Look-ahead and look-behind assertions match a group before or after a main expression without including it in the result.

Positive Look-ahead: `(?=...)`
Negative Look-ahead: `(?!...)`
Positive Look-behind: `(?<=...)`
Negative Look-behind: `(?<!...)`

These assertions are not used in this email regex.

## Examples

Valid Email Addresses
    `example@example.com`
    `user.name@domain.co`
    `user_name123@domain.io`
    `username@sub.domain.com`

Invalid Email Addresses
    `plainaddress` (missing `@` and domain)
    `@no-local-part.com` (missing local part)
    `Outlook Contact <outlook-contact@domain.com>` (name and address)
    `no-at.domain.com` (missing `@`)
    `no-tld@domain` (missing top-level domain)
    `user@.invalid.com` (invalid domain)

## Author

This tutorial was created by [Cedric Simpkins](https://github.com/github-cedsim).
