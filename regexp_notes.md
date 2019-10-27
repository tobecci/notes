# My notes on Regular Expressions

* `/tobecci/g` matches tobecci

## character sets

* `/[st]obecci/` matches sobecci or tobecci, i.e square bracket occupies one character position
``

## exclude set

* `[^hel]eso` matches everything except those starting with the characters inside the square brackets

## Ranges

* `[a-z]inja` matches any character btw a and z but does not include uppercase
* `[a-zA-Z]inja` includes uppercase


## multiples
* `[0-9]+` matches numbers from one and above length
* `[0-9]{11}` matches 11 characters that are numbers
* `[0-9]{11,20}` matches btw 11 and 20
* `[0-9]{11,}` matches at least 11 chars

## Metacharacters

* `\d` any digits
* `\w` matches `a-z A-Z 0-9 _`
* `\s` whitespace, space tabs etc
* `\t` matches tab

## special characters

* `+` quantifier
* `\` escape
* `[]` character set
* `[^]` negate symbol
* `?` zero or one quantifier(makes preceding character optional)
* `.` any character whatsoever(except whitespace)
* `*` zero or more quantifier(kinda like +)

## starting and ending patterns
`^\w{6}$` matches exactly 6 characters not more not less

## alternate characters

`(p|t)yre` matches pyre or tyre



