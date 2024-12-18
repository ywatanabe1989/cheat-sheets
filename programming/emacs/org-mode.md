
#+TITLE: Emacs Org Mode Cheat Sheet
#+LINK: manual https://orgmode.org/manual/
#+OPTIONS: toc:2 num:nil

* Introduction
[[manual][The Org Manual]]

* Basic Structure
** Headlines & Visibility
- Use asterisks (*) for levels
- TAB: Cycle local visibility
- S-TAB: Cycle global visibility
- C-c C-n/p: Next/previous heading
- M-UP/DOWN: Move heading up/down

** TODO System
*** Basic TODO States
- C-c C-t: Rotate TODO states
- S-LEFT/RIGHT: Cycle states
- Default: TODO -> DONE

*** Custom States
#+begin_src elisp
(setq org-todo-keywords
      '((sequence "TODO" "IN-PROGRESS" "WAITING" "|" "DONE" "CANCELLED")))
#+end_src

** Lists & Checkboxes
- Unordered: "-" or "+"
- Ordered: "1." or "1)"
- Checkboxes: "- [ ]"
- C-c C-c: Toggle checkbox
- M-RET: New item
- M-S-RET: New checkbox item

** Links & Navigation
- Basic: [[file:path][description]]
- C-c C-l: Insert link
- C-c C-o: Open link
- C-c %: Record position
- C-c &: Jump back

** Tables
| Key     | Action             |
|---------+--------------------|
| TAB     | Next cell         |
| S-TAB   | Previous cell     |
| M-LEFT  | Move column left  |
| M-RIGHT | Move column right |
| M-S-UP  | Add row above    |

** Source Blocks
#+begin_src
- C-c C-c: Execute block
- C-c ': Edit in buffer
- C-c C-v b: Execute buffer
#+end_src

** Export
C-c C-e brings up Export menu:
- h: HTML
- l: LaTeX/PDF
- a: ASCII
- m: Markdown

** Agenda Views
- C-c a t: Show TODO list
- C-c a a: Week agenda
- C-c a m: Match search
- C-c a s: Search
