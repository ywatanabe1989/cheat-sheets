# Emacs Regexp Replace Cheat Sheet

## Basic Commands

| Command | Description |
|---------|-------------|
| `M-x replace-regexp` | Start regexp replace |

## Basic Syntax

| Symbol | Meaning |
|--------|---------|
| `^` | Beginning of line |
| `$` | End of line |
| `.` | Any single character |
| `*` | Zero or more occurrences |
| `+` | One or more occurrences |
| `?` | Zero or one occurrence |
| `\` | Escape special characters |

## Character Classes

| Expression | Meaning |
|------------|---------|
| `[...]` | Match any character inside brackets |
| `[^...]` | Match any character not inside brackets |

## Grouping and Backreferences

| Expression | Meaning |
|------------|---------|
| `\( \)` | Group expressions |
| `\1`, `\2` | Refer to grouped expressions in replacement |

## Special Replacement Symbols

| Symbol | Meaning |
|--------|---------|
| `\&` | Entire matched text |
| ```\` ``` | Text before match |
| `\'` | Text after match |

## Common Expressions

| Expression | Meaning |
|------------|---------|
| `\w` | Word character |
| `\W` | Non-word character |
| `\s` | Whitespace |
| `\S` | Non-whitespace |
| `\b` | Word boundary |

## Examples

| Regexp | Description |
|--------|-------------|
| `\<\w+\>` | Whole word |
| `^.*$` | Entire line |
| `\([a-z]+\)\1` | Repeated word (e.g., "the the") |
| `\b[A-Z][a-z]*\b` | Capitalized word |
| `[0-9]{3}-[0-9]{3}-[0-9]{4}` | US phone number format |
| `\b\w+@\w+\.\w+\b` | Simple email address |
| `^#.*` | Comment lines starting with # |
| `\s+$` | Trailing whitespace |
| `<[^>]+>` | HTML tags |
| `\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b` | IP address |

## Practice

| Task | Regexp | Replacement |
|------|--------|-------------|
| Convert "color" to "colour" | `\bcolor\b` | `colour` |
| Remove HTML tags | `<[^>]+>` | ` ` (empty string) |
| Format phone numbers (123456789 to 123-456-789) | `(\d{3})(\d{3})(\d{3})` | `\1-\2-\3` |
| Capitalize first letter of each word | `\b(\w)(\w+)\b` | `\,(upcase \1)\2` |
| Remove duplicate words | `\b(\w+)\s+\1\b` | `\1` |
| Comment out lines containing "TODO" | `^(.*TODO.*)$` | `# \1` |
| Extract URLs from text | `https?://\S+` | `\&` (to extract) |
| Wrap words in quotes | `\b(\w+)\b` | `"\1"` |
| Remove trailing whitespace | `\s+$` | ` ` (empty string) |
| Convert snake_case to camelCase | `_(\w)` | `\,(upcase \1)` |
