# Regular Expression(Regex)入门

## Genernal

Metacharacter | Description | Exmaple
------------  | ----------- | -------
\ | 转义 | `\.` or `\\`
. | Any Character Except New Line |
\d | Digit (0-9) | 321-555-4321 - `\d\d\d-\d\d\d-\d\d\d\d`
\D | Not a Digit (0-9) |
\w | Word Character (a-z, A-Z, 0-9, _) |
\W | Not a Word Character
\s | Whitespace (space, tab, newline)
\S | Not Whitespace (space, tab, newline) |
 | |
\b | **Word** Boundary | Ha HaHa - `\bHa or \bHa\b` 
\B | Not word Boundary | Ha HaHa - `\BHa`
^ | Begining of a **String** 仅一行的开头match| Ha Haha - `^Ha`
$ | End of a **String** 仅一行的结尾match| Ha Haha - `Ha$`
 | |
[] | Matches Charachters in brackets | `\d\d\d[-.]\d\d\d[-.]\d\d\d\d` or `[89]00[-.]\d\d\d[-.]\d\d\d\d` or `[a-zA-Z0-9]`
[^] | Matches Charachter NOT in brackets | `[^a-z]` or `[cmp]at` or `[^b]at`
\| | Either Or |
（）| Group | `M(r|s|rs)\.?\s[A-Z]\w*` or `https?://(www)?.(\w)+.(com|gov) and $1, $2, $3 for specified group`
**Quantifiers** | |
\* | 0 or More, {0,} | `Mr\.?\s[A-Z]\w*`
\+ | 1 or More, {1,} | `Mr\.?\s[A-Z]\w+`
? | 0 or One, {0, 1} | `https?://(www)?.\w+.\w+`
{3} | Exact Number | `\d{3}[-.]\d{3}[-.]\d{4}`
{3,4} | Range of Numbers (Minimum, Maximum)

Below is **Text Example：**

```Text
Ha HaHa dfd
Ha HaHa

321-555-4321
123.555.1234
900-555-4321
800-555-4321

cat
mat
pat
bat

Mr. Schafer
Mr Smith
Ms Davis
Mrs Robinson
Mr. T

https://www.google.com
http://coreyms.com
https://youtube.com
https://www.nasa.gov
```

## Popular Regex List

## Reference

- [Regular Expressions (Regex) Tutorial: How to Match Any Pattern of Text](https://www.youtube.com/watch?v=sa-TUpSx1JA)