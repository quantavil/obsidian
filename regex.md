# [Regex Cheat-sheet](https://www.geeksforgeeks.org/python-regex-cheat-sheet/)
[2](https://quickref.me/regex) [3](https://github.com/bansalnitish/REGularEXpressions)

## Metacharacters
1.  `.` : Matches any character except line breaks. Equivalent to `[^\n\r]`.
2. `*` : Matches 0 or more repetitions of the preceding symbol.
3. `+` : Matches 1 or more repetitions of the preceding symbol.
4. `?` : Matches 0 or 1 of the preceding token, effectively making it optional.

## Anchors 
Anchors are unique in that they match a position within a string, not a character.

1.  `^` : Matches the expression to its right, at the start of a string before it experiences a line break
2.  `$` : Matches the expression to its left, at the end of a string before it experiences a line break
3. `\b` : Matches the word boundary (or empty string) at the start and end of a word.
4.  `\B` : Matches any position that is not a word boundary. This matches a position, not a character. or Inverse of `\b`


### A bit more about `\b`

`\b` may be a bit confusing to some of you so I tried to expand this a bit more. `\b` is an anchor like the caret and the dollar sign. It matches at a position that is called a "word boundary". This match is zero-length.

There are three different positions that qualify as word boundaries:
-   Before the first character in the string, if the first character is a word character.
-   After the last character in the string, if the last character is a word character.
-   Between two characters in the string, where one is a word character and the other is not a word character.

> A word character is all alphanumeric alphabets `[a-zA-Z0-9]` and underscore `_`. Any character not a word character is non word or not a word character.

A few examples will may you much clear about how `\b` works. The regex `\bcat\b` would match cat in a black cat, but it wouldn't match it in catatonic, tomcat or certificate. Removing one of the boundaries, `\bcat` would match cat in catfish, and `cat\b` would match cat in tomcat, but not vice-versa. Both, of course, would match cat on its own. The `\bcat\b` will not match cat in \_cat or in cat25 because there is no boundary between an underscore and a letter, nor between a letter and a digit: these all belong to what regex defines as word characters (as defined above).

```
"\bm" => moon
```

`oo\b` does not match the `oo` in "moon", because `oo` is followed by `n` which is a word character.

`\B` matches all positions where \b doesn't match. Therefore, it matches:

-   When neither side is a word character, for instance at any position in the string $=(@-%++) (including the beginning and end of the string)
-   When both sides are a word character, for instance between the `H` and the `i` in `Hi!`.

## Set
A set is a set of characters inside a pair of square brackets `[]` with a special meaning:
1. `[abc]`  : Matches either a, b, or c. It does not match abc.
2. `[^ab5]` : Adding ^ excludes any character in the set. Here, it matches characters that are not a, b, or 5.
3. `[A-Z]` : Matches any alphabets in capital from A to Z
4. `[a\-p]` : Matches a, -, or p. It matches – because `\` escapes it.
5. `[a-z0-9]` : Matches characters from a to z or from 0 to 9.
6. `[(+*)]`  : Special characters become literal inside a set, so this matches `(`, `+`, `*`, `)`

## Meta Sequences
`\w` :	Matches alphanumeric characters: `[a-zA-Z0-9_]`
`\W` :	Matches non-alphanumeric characters: `[^\w]`
`\d` :	Matches digit: `[0-9]`
`\D` :	Matches non-digit: `[^\d]`
`\s` :	Matches whitespace character: `[\t\n\f\r\p{Z}]`
`\S` :	Matches non-whitespace character: `[^\s]`

## Quantifiers

1. `{p}` : Matches the expression to its left p times, and not less. 
2. `{p,q}` : Matches the expression to its left p to q times, and not less.
3. `{p,}` : Matches the expression to its left p or more times.
4. `{,q}` : Matches the expression to its left up to q times

## Group Constructs

1. `()` :  Matches the expression inside the parentheses and groups it which we can capture as required
2. `(a|b)` :Match either a or b



---
# Common Regular Expression Patterns 

1.  Comments that has either `#`  or `;`   and `.*` matches anything else in the line.  :  ```
```bash
^[#;].*
```

2.  All blank Lines : ```
```bash
^(?:[\t ]*(?:\r?\n|\r))+
```

3.  U+00a0 (&nbsp) : 
```bash
[\xa0]
```



