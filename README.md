# Understanding Email Validation Regex

Github Gist Link

https://gist.github.com/sagagi74/cd6a2f2bea6c26dad79cadd4d41cfe8d


## Introductory

The purpose of this tutorial is to explain what regex is and how it can be used to match an email. We'll be using the following regex for matching an email:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Summary

This tutorial explains how a specific regular expression, or regex (regex for matching an email), functions by breaking down each part of the expression and describing what it does.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors are used to ensure that the regex matches from the start or end of the string.

- `^`: Asserts the position at the start of the string.
- `$`: Asserts the position at the end of the string.

In our regex: `^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$`
- The `^` at the beginning ensures the string starts with the specified pattern.
- The `$` at the end ensures the string ends with the specified pattern.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.

- `+`: Matches one or more of the preceding element.

In our regex: `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, and `([a-z\.]{2,6})`
- The `+` after `[a-z0-9_\.-]` means one or more of the characters in the brackets.
- The `+` after `[\da-z\.-]` means one or more of the characters in the brackets.
- The `{2,6}` after `[a-z\.]` specifies that it must match between 2 and 6 characters.

### Grouping Constructs

Grouping constructs allow you to group parts of your regex together. These are useful for applying quantifiers to multiple characters and for capturing substrings to use in further processing.

In our regex: `([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`
- `([a-z0-9_\.-]+)` captures the username part of the email.
- `([\da-z\.-]+)` captures the domain name.
- `([a-z\.]{2,6})` captures the top-level domain.

### Bracket Expressions

Bracket expressions define a set of characters to match. These are also known as character classes and allow for matching any one of the characters within the brackets.

In our regex: `[a-z0-9_\.-]`, `[\da-z\.-]`, and `[a-z\.]`
- `[a-z0-9_\.-]` matches any lowercase letter, digit, underscore, dot, or hyphen.
- `[\da-z\.-]` matches any digit, lowercase letter, dot, or hyphen.
- `[a-z\.]` matches any lowercase letter or dot.

### Character Classes

Character classes match any single character from a set of characters. They are defined using square brackets and can include ranges.

In our regex:
- `[a-z0-9_\.-]` matches any character that is a lowercase letter, digit, underscore, dot, or hyphen.
- `[\da-z\.-]` matches any character that is a digit, lowercase letter, dot, or hyphen.
- `[a-z\.]` matches any character that is a lowercase letter or dot.

### The OR Operator

The OR operator (`|`) is used to match any one of several patterns. It allows for branching logic within the regex.

In our regex, we don't explicitly use the OR operator, but it can be used in other regex patterns, such as `(abc|def)` which matches either "abc" or "def".

### Flags

Flags are optional parameters that modify the behavior of the regex. They are placed at the end of the regex after a closing slash.

Common flags include:
- `i` for case-insensitive matching.
- `g` for global matching (find all matches rather than stopping after the first match).
- `m` for multi-line matching.

Our regex does not use any flags, but they can be added for additional functionality.

### Character Escapes

Character escapes are used to include special characters in the regex. These characters usually have a special meaning in regex syntax and need to be escaped with a backslash (`\`) to be matched literally.

In our regex:
- `\.` is used to match a literal dot, since a dot normally matches any character.
- `\d` is used to match any digit.

## Author

This tutorial was written by [YongYun](https://github.com/sagagi74). I am a web development passionate about learning and teaching code.
