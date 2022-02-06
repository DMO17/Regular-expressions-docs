# Regular-expressions-docs

## Table of Content

- [Summary](#summary)

## Summary

A regex (regular expression) is a string of text that consists of a certain pattern used to match , locate and manage text/character combinations.

For example when validating the format of an email address in a form the following regex is used to check if the email contains the pattern and structure.

```
(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])
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
