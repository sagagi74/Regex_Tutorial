# Understanding Email Validation Regex

Github Gist Link

https://gist.github.com/sagagi74/cd6a2f2bea6c26dad79cadd4d41cfe8d


## Introductory

The aim of this tutorial is to elucidate the nature of regular expressions (regex) and illustrate their utility in validating email addresses. For this purpose, we will employ the following regex pattern to match an email:
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Summary

This tutorial clarifies how a particular regular expression, also known as regex (used for matching an email), operates by dissecting each component of the expression and detailing its function.

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

These are employed to guarantee that the regex matches from the beginning or end of the string.

^: Asserts the position at the beginning of the string.
$: Asserts the position at the conclusion of the string.
In our regex: ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$

The ^ at the start ensures the string commences with the specified pattern.
The $ at the end ensures the string terminates with the specified pattern.

### Quantifiers

Quantifiers determine the number of instances of a character, group, or character class that must be present in the input for a match to occur.

+: Matches one or more of the preceding element.
In our regex: ([a-z0-9_\.-]+), ([\da-z\.-]+), and ([a-z\.]{2,6})

The + following [a-z0-9_\.-] signifies one or more of the characters within the brackets.
The + following [\da-z\.-] signifies one or more of the characters within the brackets.
The {2,6} following [a-z\.] specifies that it must match between 2 and 6 characters.

### Grouping Constructs

Grouping constructs enable you to combine sections of your regex. These are beneficial for applying quantifiers to multiple characters and for capturing substrings for further processing.

In our regex: ([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})

([a-z0-9_\.-]+) captures the username portion of the email.
([\da-z\.-]+) captures the domain name.
([a-z\.]{2,6}) captures the top-level domain.

### Bracket Expressions

Bracket expressions specify a set of characters to match. These are also referred to as character classes and enable matching any one of the characters contained within the brackets.

In our regex: [a-z0-9_\.-], [\da-z\.-], and [a-z\.]

[a-z0-9_\.-] matches any lowercase letter, digit, underscore, period, or hyphen.
[\da-z\.-] matches any digit, lowercase letter, period, or hyphen.
[a-z\.] matches any lowercase letter or period.

### Character Classes

Character classes identify any individual character from a defined set of characters. They are enclosed in square brackets and can incorporate ranges.

In our regex:

[a-z0-9_\.-] matches any character that is a lowercase letter, number, underscore, dot, or hyphen.
[\da-z\.-] matches any character that is a number, lowercase letter, dot, or hyphen.
[a-z\.] matches any character that is a lowercase letter or dot.
### The OR Operator

The OR operator (|) is utilized to match any one of multiple patterns, enabling branching logic within the regex.

In our regex, we don't explicitly employ the OR operator, but it can be applied in other regex patterns, such as (abc|def), which matches either "abc" or "def".

### Flags

Flags are optional parameters that alter the behavior of the regex. They are appended at the end of the regex after a closing slash.

Common flags include:

i for case-insensitive matching.
g for global matching (finding all matches instead of stopping after the first match).
m for multi-line matching.
Although our regex does not use any flags, they can be included to provide extra functionality.

### Character Escapes


Character escapes allow the inclusion of special characters in the regex. These characters typically have a specific function in regex syntax and must be escaped with a backslash (\) to be matched literally.

In our regex:

\. is used to match an actual dot, as a dot normally matches any character.
\d is used to match any digit.

## Author

This tutorial was written by [YongYun](https://github.com/sagagi74). I am a web development passionate about learning and teaching code.
