# Email Regex Tutorial

A regex, which is short fo regular expression, is a sequence of characters that defines a specific search pattern. When coding, a regex can be used to find patterns of characters in a string, find and replace a character or sequence of characters in a string, or be used to validate an input. Each compunebt of the regex has a specific responsibility,

## Summary

The regex to verify the user input is a valid email address is /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
This tutorial will break down the regex to see how this combination of letters, numbers and symbols find and varify emails.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Summary](#summary)
- [Author](#author)

## Regex Components

### Anchors

`/^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$/`
Highlited are the anchors. These are the symbols at the begining and end of the regex to signify the start and end of the string.
    `^` is the begining of the input
    `$` is the ending of the input
Anything inbetween these symbols will be the qualifiers to find/veerify what our regex is made for, in this case emails.

### Quantifiers

/^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]`{2,6}`)$/
Qualifiers are used to communicate how many characters are expected. Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.
Qualifiers that can be found in a regex are:
    `*` match zero or more times
    `+` match one or more times
    `?` match zero or one time
    `{` n `}` match exactly n times
    `{` n `,}` match at least n times
    `{` n `,` m `}` match from n to m times
In our email example we have `{2,6}` with in the '([a-z\.]{2,6})' expresion of the regex. This is telling it that the part after the '.' of the email needs to be between 2-6 characters. We also have `+` characters that will allow the regex to match any length that is inputed.

### OR Operator

The "or" operator within a regular expression is defined using the `|` element. The or operator indicates that it could either of the components that we are separating with the `|`. But an example of this would be `gray|grey`, which can match "gray" or "grey".

### Character Classes

/^([`a-z``0-9``_``\.``-`]+)`@`([`\d``a-z``\.``-`]+)`\.`([`a-z``\.`]{2,6})$/
Character classes are components within our regular expression that tells us what type of characters to expect. Our character classes are confined with in the `[]` brackets.
    `a-z` matches lowercase letters
    `0-9` matches numbers
    `_` matches the '_' character
    `\.` matches the '.' character
    `-` matches the '-' character
    `@` matches the '@' character
    `\d` matches any digit character

### Flags

Flags are optional in regular expressions. Flags allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression. Our regex do not have any flags but exaples of these would be:
    `d` Generate indices for substring matches.
    `g` Global search.
    `i` Case-insensitive search.
    `m` Multi-line search.
    `s` Allows . to match newline characters.
    `u` "unicode"; treat a pattern as a sequence of unicode code points.
    `y` Perform a "sticky" search that matches starting at the current position in the target string.

### Grouping and Capturing

/^`([a-z0-9_\.-]+)`@`([\da-z\.-]+)`\.`([a-z\.]{2,6})`$/
The use of grouping expressions is to allow for the extraction of the characters of a given group for validation. The text between paranthesis is a group.

### Bracket Expressions

/^(`[a-z0-9_\.-]`+)@(`[\da-z\.-]`+)\.(`[a-z\.]`{2,6})$/
A bracket expression is either a matching list expression or a non-matching list expression. It consists of one or more expressions: ordinary characters, collating elements, collating symbols, equivalence classes, character classes, or range expressions.

### Greedy and Lazy Match

/^([a-z0-9_\.-]`+`)@([\da-z\.-]`+`)\.([a-z\.]{2,6})$/
A greedy match will match the longest possiple string. A lazy match will match the shortest string. In our example the `+` to allow any length to be inputed. This is handy in emails as there are no set amount of characters that users have to have.

### Summary

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

After everything we've looked at lets explain the full regex. 
    `^` we are starting the string
    `([a-z0-9_\.-]+)` we are looking at what is before the '@' character. It can be any length (`+`) of lowercase letters (`a-z`), numbers (`0-9`), and the special characters _ . - (`_\.-`).
    `@` we match the '@' character the string.
    ([\da-z\.-]+) we look at what comes after the '@' character. It can be any length (`+`) of lowercase letters (`a-z`), numbers (`\d`), and the special characters . - (`\.-`).
    `\.` we match the '.' in the string.
    `([a-z\.]{2,6})` we look at what is after the '.'. It has to be between 2-6 characters in legth (`{2,6}`) with only lowercase letters (`a-z`) and a '.' (`\.`).
All of this allows us to verify emails such as debleehall15@gmail.com is the currect format and show us that something like DebHall@g_mail.c would not pass.

## Author

Debbie Hall

Debbie Hall is a coding student at Ohio State University currently completing a certification in full-stack development. She also has a BS in Mass Communication with an imphasis in photography.

GitHub: [debleehall](https://github.com/debleehall)
