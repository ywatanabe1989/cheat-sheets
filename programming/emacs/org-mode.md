# Emacs Org Mode Cheat Sheet

## Basic Syntax

### Headlines
Use asterisks (*) for levels:
# Level 1
## Level 2
### Level 3

### TODO Items
- [ ] Becomes: TODO
- [x] Becomes: DONE

## TODO States
- Use `C-c C-t` to cycle through states: TODO -> DONE -> (none)
- Alternative: `Shift-LEFT/RIGHT` to cycle
- Customize in init.el:
```elisp
(setq org-todo-keywords
      '((sequence "TODO" "IN-PROGRESS" "WAITING" "|" "DONE" "CANCELLED")))
```
### Lists
- Unordered lists use - or +
1. Ordered lists use numbers
   - Sub-items need indentation

### Links
[Description](file:path/to/file)
[Website](https://website.com)

## Key Bindings
| Key | Action |
|-----|--------|
| TAB | Cycle visibility |
| M-RET | New heading |
| M-LEFT | Promote heading |
| M-RIGHT | Demote heading |
| C-c C-t | Toggle TODO state |

## Commands
- C-c C-c: Execute code block
- C-c ': Edit code block
- C-c C-e: Export menu
