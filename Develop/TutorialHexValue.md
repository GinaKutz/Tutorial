# Matching a Hex Value Tutorial

In this tutorial, we'll explore regular expressions and how they can be used to match hex color codes. Hex color codes are commonly used in web development to specify colors. Regular expressions provide a powerful way to search for patterns within strings, making them ideal for tasks like matching hex color codes.

## Summary

The regular expression <code>/^#?([a-f0-9]{6}|[a-f0-9]{3})$/</code> matches hex color codes. It starts with an optional <code>#</code> symbol followed by either three or six characters in the range of <code>a-f</code> and <code>0-9</code>. This regex provides a concise and effective way to validate hex color codes.



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

## Anchors

Explanation of how anchors (^ and $) are used to match the beginning and end of a string respectively.

^ (caret):

The caret (^) symbol is used as an anchor to match the beginning of a string.
When the caret (^) is placed at the beginning of a regex pattern, it asserts that the following pattern must occur at the beginning of the string.
For example, the regex pattern ^hello will match any string that starts with "hello", such as "hello world" or "hello there", but it will not match "world hello".
If the caret (^) is used outside of a character set (inside brackets []), it matches the beginning of the string. For example, ^[a-z] will match any string that starts with a lowercase letter.
$ (dollar):

The dollar ($) symbol is used as an anchor to match the end of a string.
When the dollar ($) is placed at the end of a regex pattern, it asserts that the preceding pattern must occur at the end of the string.
For example, the regex pattern world$ will match any string that ends with "world", such as "hello world" or "goodbye world", but it will not match "world hello".
If the dollar ($) is used outside of a character set (inside brackets []), it matches the end of the string. For example, [0-9]$ will match any string that ends with a digit.

Here's a summary:

^ (caret) matches the beginning of a string.
$ (dollar) matches the end of a string.
When used together, ^$ matches an empty string, effectively asserting that the entire string matches the given pattern.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Quantifiers

Explanation of quantifiers (+, *, ?, {n}, {n,}, {n,m}) and their usage in regex.

+ (plus):

The plus (+) quantifier matches one or more occurrences of the preceding element.
For example, the regex pattern a+ will match one or more occurrences of the letter "a" in a string. It will match "a", "aa", "aaa", and so on, but not an empty string or a string without any "a" characters.

* (asterisk):

The asterisk (*) quantifier matches zero or more occurrences of the preceding element.
For example, the regex pattern b* will match zero or more occurrences of the letter "b" in a string. It will match an empty string, "b", "bb", "bbb", and so on.

? (question mark):

The question mark (?) quantifier matches zero or one occurrence of the preceding element.
For example, the regex pattern c? will match zero or one occurrence of the letter "c" in a string. It will match an empty string or "c".

{n} (exact):

The {n} quantifier matches exactly n occurrences of the preceding element.
For example, the regex pattern d{3} will match exactly three occurrences of the letter "d" in a string. It will match "ddd" but not "dd" or "dddd".

{n,} (at least n):

The {n,} quantifier matches n or more occurrences of the preceding element.
For example, the regex pattern e{2,} will match two or more occurrences of the letter "e" in a string. It will match "ee", "eee", "eeee", and so on.

{n,m} (between n and m):

The {n,m} quantifier matches between n and m occurrences of the preceding element.
For example, the regex pattern f{2,4} will match between two and four occurrences of the letter "f" in a string. It will match "ff", "fff", or "ffff" but not "f" or "fffff".

Quantifiers are powerful tools in regex that allow you to specify flexible patterns to match varying lengths of text. They provide control over the number of occurrences of a particular element in a string.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## OR Operator

Explanation of the OR operator (|) and its usage in regex.

| (OR operator):
The vertical bar (|) is used as the OR operator in regex.
It allows you to specify multiple alternative patterns, separated by the OR operator, within a single regex pattern.
The OR operator matches either the pattern on its left side or the pattern on its right side.
It is useful when you want to match different variations of a pattern or multiple distinct patterns at a particular position in the string.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Character Classes

Explanation of character classes ([], [^], \d, \w, \s) and their usage in regex.

[] (square brackets):

Square brackets [] are used to define a character class.
Inside the square brackets, you list the characters you want to match. Any character inside the brackets will be considered a match.
For example, the regex pattern [aeiou] matches any vowel character (a, e, i, o, or u).
You can also specify ranges of characters using a hyphen (-). For example, [0-9] matches any digit character (0 to 9).

[^] (caret inside square brackets):

When the caret (^) is placed at the beginning of a character class inside square brackets, it negates the character class.
It matches any character that is not listed inside the square brackets.
For example, the regex pattern [^0-9] matches any character that is not a digit.

\d (digit):

\d is a shorthand character class that matches any digit character.
It is equivalent to the character class [0-9].
For example, \d matches any digit character (0 to 9).

\w (word character):

\w is a shorthand character class that matches any word character.
It matches alphanumeric characters (letters, digits, and underscores).
It is equivalent to the character class [a-zA-Z0-9_].
For example, \w matches any letter, digit, or underscore character.

\s (whitespace):

\s is a shorthand character class that matches any whitespace character.
It matches spaces, tabs, and newline characters.
For example, \s matches any whitespace character.

Character classes provide a powerful way to match specific sets of characters in a string. They allow you to define patterns that match a wide range of characters with minimal syntax.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Flags

Explanation of flags (g, i, m, u, y) and their usage in regex.

g (global):

The global flag, indicated by "g" after the regex pattern, enables global matching.
When the global flag is set, the regex engine continues searching for all matches in the input string rather than stopping after the first match.
For example, /pattern/g will find all occurrences of "pattern" in the input string.

i (ignore case):

The ignore case flag, indicated by "i" after the regex pattern, makes the pattern case insensitive.
When the ignore case flag is set, the regex engine matches characters regardless of their case.
For example, /pattern/i will match "pattern", "Pattern", "PATTERN", etc., in the input string.

m (multiline):

The multiline flag, indicated by "m" after the regex pattern, enables multiline mode.
When the multiline flag is set, the ^ and $ anchors match the beginning and end of each line within the input string, rather than just the beginning and end of the entire string.
For example, /^pattern$/m will match "pattern" at the beginning of a line and at the end of a line within the input string.

u (unicode):

The unicode flag, indicated by "u" after the regex pattern, enables full Unicode matching.
When the unicode flag is set, the regex engine treats the input string and pattern as Unicode strings, allowing it to match Unicode characters correctly.
This flag is particularly useful when working with Unicode characters or when using Unicode property escapes in the regex pattern.

y (sticky):

The sticky flag, indicated by "y" after the regex pattern, enables sticky matching.
When the sticky flag is set, the regex engine matches starting from the index specified by the lastIndex property of the RegExp object.
This flag is useful when you want to perform a search starting from a specific index within the input string.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Grouping and Capturing

Explanation of grouping (()) and capturing in regex.

Grouping (( )):

Parentheses (( )) are used to create a group within a regex pattern.
Inside the parentheses, you can specify a subpattern that you want to treat as a single unit.
Groups are useful for applying quantifiers, alternation, or other operators to multiple characters or subpatterns.
For example, the regex pattern (abc)+ matches one or more occurrences of the sequence "abc" in the input string.

Capturing (( )):

Capturing parentheses (( )) not only create a group but also capture the matched substring for later use.
When a regex pattern contains capturing groups, the substrings that match the groups are stored in memory.
You can refer to the captured substrings using back-references or access them programmatically after a match is found.
For example, in the regex pattern (\d{2})-(\d{2})-(\d{4}), there are three capturing groups that capture the day, month, and year components of a date in the format "dd-mm-yyyy".

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Bracket Expressions

Explanation of bracket expressions ([], [^]) and their usage in regex.

[] (square brackets):

Square brackets [] are used to define a character class or bracket expression.
Inside the square brackets, you list the characters you want to match. Any character inside the brackets will be considered a match.
For example, the regex pattern [aeiou] matches any vowel character (a, e, i, o, or u).
You can specify individual characters, ranges of characters, or a combination of both inside the square brackets.

[^] (caret inside square brackets):

When the caret (^) is placed at the beginning of a character class inside square brackets, it negates the character class.
It matches any character that is not listed inside the square brackets.
For example, the regex pattern [^0-9] matches any character that is not a digit.
This is useful when you want to match any character except those listed inside the square brackets.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Greedy and Lazy Match

Explanation of greedy and lazy matching in regex.

Greedy Matching:

Greedy matching is the default behavior of quantifiers in regular expressions.
A greedy quantifier tries to match as much of the input string as possible while still allowing the overall pattern to match.
For example, in the regex pattern .*, the asterisk (*) quantifier is greedy. It matches zero or more occurrences of any character (.), consuming as many characters as possible while still allowing the pattern to match.
Greedy quantifiers are indicated by adding a question mark (?) after the quantifier. For example, *?, +?, ??, {n,}?, {n,}?, etc.

Lazy (or Reluctant) Matching:

Lazy matching, also known as reluctant or non-greedy matching, is the opposite behavior of greedy matching.
A lazy quantifier matches as little of the input string as possible while still allowing the overall pattern to match.
Lazy quantifiers are indicated by adding a question mark (?) after the greedy quantifier. For example, *?, +?, ??, {n,}?, {n,}?, etc.
For example, in the regex pattern .*?, the asterisk (*) quantifier is lazy. It matches zero or more occurrences of any character (.), consuming as few characters as possible while still allowing the pattern to match.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Boundaries

Explanation of word boundaries (\b) and line boundaries (^, $) in regex.

Word Boundaries (\b):

The word boundary (\b) is a zero-width assertion that matches the position between a word character (\w) and a non-word character (\W), or between the beginning/end of a string and a word character.
Word characters include letters, digits, and underscores ([a-zA-Z0-9_]).
For example, the regex pattern \bword\b will match the word "word" when it appears as a separate word in the string, but not when it's part of another word like "password" or "wordsmith".
Word boundaries are useful for matching whole words and avoiding partial matches within longer words.

Line Boundaries (^ and $):

The caret (^) and dollar ($) symbols are used to match the beginning and end of a line, respectively.
The caret (^) asserts the position at the beginning of a line.
The dollar ($) asserts the position at the end of a line.
For example, the regex pattern ^start will match "start" only if it appears at the beginning of a line, and the pattern end$ will match "end" only if it appears at the end of a line.
Line boundaries are useful for matching patterns at the beginning or end of lines in multiline strings.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Back-references

Explanation of back-references (\1, \2) and their usage in regex.

\1, \2, etc.:
Back-references are indicated by a backslash () followed by a digit (1, 2, 3, etc.).
The digit corresponds to the index of the capturing group you want to refer to.
For example, \1 refers to the first capturing group, \2 refers to the second capturing group, and so on.
You can use back-references inside the same regex pattern to match the same text that was previously matched by a capturing group.
Back-references are particularly useful for matching repeated patterns or enforcing consistency within a regex pattern.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`

## Look-ahead and Look-behind

Explanation of look-ahead (?=) and look-behind (?<=) assertions in regex.

Positive Look-ahead (?=):

Positive look-ahead (?=) asserts that a particular pattern must be followed by another pattern at a specific position in the string.
It matches the current position in the string only if the pattern inside the look-ahead assertion matches the characters that follow.
The pattern inside the look-ahead assertion is not included in the match.
For example, the regex pattern foo(?=bar) will match "foo" only if it is followed by "bar".
Positive look-ahead assertions are useful for defining patterns based on the presence or absence of certain characters without including them in the match.
Negative Look-ahead (?!):

Negative look-ahead (?!), similar to positive look-ahead, asserts that a particular pattern must not be followed by another pattern at a specific position in the string.
It matches the current position in the string only if the pattern inside the negative look-ahead assertion does not match the characters that follow.
The pattern inside the negative look-ahead assertion is not included in the match.
For example, the regex pattern foo(?!bar) will match "foo" only if it is not followed by "bar".
Negative look-ahead assertions are useful for defining patterns based on the absence of certain characters without including them in the match.
Positive Look-behind (?<=):

Positive look-behind (?<=) asserts that a particular pattern must be preceded by another pattern at a specific position in the string.
It matches the current position in the string only if the pattern inside the look-behind assertion matches the characters that precede it.
The pattern inside the look-behind assertion is not included in the match.
For example, the regex pattern (?<=foo)bar will match "bar" only if it is preceded by "foo".
Positive look-behind assertions are useful for defining patterns based on the characters that precede the match without including them in the match.
Negative Look-behind (?<!):

Negative look-behind (?<!), similar to positive look-behind, asserts that a particular pattern must not be preceded by another pattern at a specific position in the string.
It matches the current position in the string only if the pattern inside the negative look-behind assertion does not match the characters that precede it.
The pattern inside the negative look-behind assertion is not included in the match.
For example, the regex pattern (?<!foo)bar will match "bar" only if it is not preceded by "foo".
Negative look-behind assertions are useful for defining patterns based on the absence of certain characters without including them in the match.

Example: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`


## Author

Gina Kutz is a Stay at home mom who is new to coding and taking the class to work on a project for her son. 
https://github.com/GinaKutz
