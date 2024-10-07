# Emacs Regexp Replace Cheat Sheet

## Basic Commands
- `M-x replace-regexp`: Start regexp replace

## Basic Syntax
- `^`: Beginning of line
- `$`: End of line
- `.`: Any single character
- `*`: Zero or more occurrences
- `+`: One or more occurrences
- `?`: Zero or one occurrence
- `\`: Escape special characters

## Character Classes
- `[...]`: Match any character inside brackets
- `[^...]`: Match any character not inside brackets

## Grouping and Backreferences
- `\( \)`: Group expressions
- `\1`, `\2`: Refer to grouped expressions in replacement

## Special Replacement Symbols
- `\&`: Entire matched text
- ```\` ```: Text before match
- `\'`: Text after match

## Common Expressions
- `\w`: Word character
- `\W`: Non-word character
- `\s`: Whitespace
- `\S`: Non-whitespace

## Examples
- `\<\w+\>`: Whole word
- `^.*$`: Entire line
