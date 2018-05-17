##  Lexical structure
- JS characters are unicode based.
- JS is caseSensitive language
- Comments are line based, and block based. // or /* block of comments */

## Idnetifier, and Reserved words
- ECMAScript 3 took evey reserved words from Java.\
- ECMAScript 5 relaxed in these words and removed some them. But it added some reserved words for the `strict mode`, and `furtur versions`

## Semicolons
- It is optional, but USE it please.
- Rule of thumb: JS doenst treat every line break as a semi-colons; it usually treats line breaks as semicolon only if it cant parse the code without the semicolons.
- Other way around: JS interpretes a line break as a semicolon if it appears after `return`, `break`, `continue`, or before `++` or `--` operators or if the next nonstop characater cannot be interpreted as a continuation fo the current statement.
