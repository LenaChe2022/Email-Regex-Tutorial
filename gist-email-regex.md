# Email Regular Expression Tutorial

In this tutorial I want to describe how a specific regular expression, or regex, functions by breaking down each part of the expression and describing what it does. My example of regex is used to match Email addresses: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
Let's break it down for componets.

## Summary

So in summary, the regular expression `/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/` matches an email address that consists of a username, followed by the @ symbol, followed by a domain name, and finally a top-level domain (TLD) that is between 2 and 6 characters long. The captured groups can be used to extract the username, domain name, and TLD from the email address.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

* The first character is a forward slash `/`, which starts the regular expression.
* `^` indicates the start of the string that will be matched.
* `([a-z0-9_\.-]+)` matches one or more characters that are either lowercase letters (a-z), digits (0-9), underscores (_), periods (.), or hyphens (-), and stores them as a capturing group.
* `@` matches the @ symbol that separates the username and domain name in an email address.
`([\da-z\.-]+)` matches one or more characters that are either digits (\d), lowercase letters (a-z), periods (.), or hyphens (-), and stores them as another capturing group.
* `\.` matches a period character.
* `([a-z\.]{2,6})` matches two to six characters that are either lowercase letters (a-z) or periods (.), and stores them as a capturing group. This represents the top-level domain (TLD) of the email address.
* `$` indicates the end of the string that will be matched.

### Anchors

There are two anchors in this regular expression: `^` and `$`.

The `^` anchor matches the start of a line or string, and `$` matches the end of a line or string with the characters that precede it. In this regular expression, they are used to ensure that the entire string matches the pattern.

So `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` means that the regular expression should match the entire string starting from the beginning of the line (or string) with the pattern matching a username, followed by an `@` symbol, followed by a domain name, and ending with a TLD that is between 2 and 6 characters long.

If the input string doesn't start with the pattern specified by the regular expression or doesn't end with the pattern, the regular expression won't match.

### Quantifiers

Quantifiers are used in regular expressions to specify how many times a particular character or group of characters should be matched. The following quantifiers are present in this regular expression:

* `+` matches one or more occurrences of the preceding character or group of characters. For example, `([a-z0-9_\.-]+)` matches one or more occurrences of lowercase letters, digits, underscores, periods, or hyphens. Similarly, `([\da-z\.-]+)` matches one or more occurrences of digits, lowercase letters, periods, or hyphens.

* `{2,6}` matches the preceding character or group of characters between two and six times. In this regular expression, it is used to match the top-level domain (TLD), which can have between 2 and 6 characters.

So, the regular expression I exploring, `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`, uses quantifiers to match one or more occurrences of specific characters and to specify the number of occurrences of the TLD.

### Grouping Constructs

Grouping constructs are used in regular expressions to group together a set of characters or expressions so that they can be treated as a single unit. The primary way you group a section of a regex is by using parentheses `()`. Each section within parentheses is known as a subexpression. In this regular expression, there are three sets of parentheses used for grouping:

* `([a-z0-9_\.-]+)`: This is the first capturing group and matches one or more occurrences of lowercase letters, digits, underscores, periods, or hyphens in the username portion of the email address.

* `([\da-z\.-]+)`: This is the second capturing group and matches one or more occurrences of digits, lowercase letters, periods, or hyphens in the domain name portion of the email address.

* `([a-z\.]{2,6})`: This is the third capturing group and matches two to six occurrences of lowercase letters or periods in the top-level domain (TLD) portion of the email address.

By using parentheses to group together these sets of characters, you can treat them as single units and apply quantifiers and other operations to them as a whole. Additionally, the capturing groups allow you to extract specific portions of the matched text. Unlike bracket expressions, subexpressions look for an exact match unless they're told to do otherwise.

### Bracket Expressions

Bracket expressions, also known as a positive character group, are used in regular expressions to match any one character from a specified set of characters. In this regular expression, there are several bracket expressions used:

* `[a-z0-9_\.-]`: This matches any any combination of lowercase letter, digit, underscore, period, or hyphen in the username portion of the email address.

* `[\da-z\.-]`: This matches any any combination of digit, lowercase letter, period, or hyphen in the domain name portion of the email address.

* `[a-z\.]`: This matches any any combination of lowercase letter or period in the top-level domain (TLD) portion of the email address.

In each case, the characters enclosed in square brackets represent a set of characters that can be matched. By using bracket expressions, we can specify a range of possible characters that can be matched, without having to explicitly list out each possible character.

### Character Classes

A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. This regular expression contains the following character classes:

* `[a-z]`: Matches any lowercase letter from a to z.

* `[0-9]`: Matches any digit from 0 to 9.

* `[_]`: Matches an underscore character.

* `[-]`: Matches a hyphen character.

* `\d`: Matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.

The character classes are used to match specific sets of characters within the email address.

### Character Escapes

The backslash `\` in a regex escapes a character that otherwise would be interpreted literally. The following character escape is used in Email regular expression:

* `\.`: This character escape matches any period literary. Otherwise a simple `.` could match any character.
In my examle of email regex there is no need to use backslash as a character escape before period inside the bracket expressions like this part `[a-z0-9_\.-]`, because all special characters, including the backslash (\), lose their special significance inside bracket expressions.


## Author

My GitHub profile: https://github.com/LenaChe2022

With additional questions contact me by email: lenache2022@gmail.com
