# Regular-expressions-docs

## Table of Content

- [Summary](#summary)
- [Regex Components](#regex-components)
  - [Anchors](#anchors)
  - [Bracket Expressions](#bracket-expressions)
  - [Quantifiers](#quantifiers)
- [Author](#author)

## Summary

A regex (regular expression) is a string of text that consists of a certain pattern used to match , locate and manage text/character combinations.

For example when validating the format of an email address in a form the following regex is used to check if the email contains the pattern and structure.

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

The regex above illustrates that an email string must be seperated into two parts by the `@` symbol e.g `username@domain`. When it comes to the length of the string, the first part of the email may contain up to 64 characters and the domain section may contain up to 253 characters.

The username section of the email can only contain the following characters according to the regex

- Uppercase Letters from (A-Z)
- Lowercase Letters from (a-z)
- Digits from (0-9)
- Characters ! # $ % & ' \* + - / = ? ^ \_ ` { | } ~

When it comes to the domain name part of the email it can container letters, digits, hyphens, and dots.

```
reg.test( helloWorld@javascript.com)
reg.test( hello.World1@javascript.node)
reg.test( hello@developer.com)
// expected outputs : true
```

```
reg.test( helloWorld.javascript.com)  // no `@` symbol present
reg.test( @helloWorld.javascript.com) // no characters before@ symbol
reg.test( helloWorld@.javascript.com) // The domain cannot start with a full-stop (.)
reg.test( .helloWorld@javascript.com) // The username section cannot start with a full-stop (.)
// expected outputs : false

```

When an email address is compared to the regex above it will always return a boolean response of `true` or `false` weather or not the string contains the pattern of the regex.

## Regex Components

### Anchors

Anchors are not classified as regex components that match any characters at all. But instead they are used to identify and match the position of a character in a string to a pre-determined location.

The 2 main anchors used to in regex to signify the beginning and end of a string respectively are `^` and `$`. The `^` anchor denotes that a string begins the character that follow it. While the `$` anchor signifies that ends with a character that precede it. In both cases it can be preceded by an exact string or a range of possible values.

#### Examples:

- `^Hello`: This matches any string starts with `Hello`, but not `hello` as regex are case-sensitive
- `javascript$`: This matches any string that ends with `javascript`
- `^Hello World$`: This is an exact string match, where the string must start and end with `Hello World`
- `Test`: Matches any string that has the text Test in it

#### Anchors table

| Syntax | Description | Example |
| ------ | ----------- | ------- |
| \A     |             |         |
|        |             |         |

### Bracket Expressions

Bracket expressions also known as positive character group represents a range of allowable characters with the square brackets `[]`. For example the regex`[123]` will accept any string regardless of its length as long as it consists of either `1` or `2` or `3` so therefore the following strings are acceptable `iuefgne2` , `1oir3ener` , `12`.

In bracket expresisons hyphens (-) are used between alphanumeric characters to represent a range of those possible values. E.g [1-5] means [12345]. Also parentheses () are used to group parts of a regex together in to subgroups like `([\da-z\.-]+)`.

#### Bracket expression Examples and meaning

| Syntax      | Meaning                                                                                                    |
| ----------- | ---------------------------------------------------------------------------------------------------------- |
| [a-z]       | This looks for strings that contain any lowercase letter characters between                                |
| [a-zA-Z]    | This looks for strings that contain any uppercase letter characters between                                |
| [0-9]       | This looks for strings that contain any whole number / integer                                             |
| [ _- /$!% ] | This looks for any string that contains any of the special characters that are specified in the expression |

### Quantifiers

Qualifiers are used to outline the number of times they would like a particular regex string to match. They often include the range of characters your regex allows a string to consist. Also Quantifiers are inherently greedy, meaning they match as many occurrences of particular patterns as possible. They include the following;

- `*`: Matches the pattern zero or more times
- `+`: Matches the pattern one or more times
- `?`: Matches the pattern zero or more times (lazy quantifier)
- `{ n }`: Matches the pattern exactly `n` times
- `{ n, }`: Matches the pattern at least `n` times
- `{ n , x }`: Matches the pattern from a minimum of `n` times to a maximum of `x` times

## Author
