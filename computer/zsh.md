# ZSH

Default emacs keymap bindings.

## Movement

| Key | Widget | Action |
|-----|--------|--------|
| `^A` | `beginning-of-line` | Start of line |
| `^E` | `end-of-line` | End of line |
| `^B` | `backward-char` | Back one char |
| `^F` | `forward-char` | Forward one char |
| `M-b` | `backward-word` | Back one word |
| `M-f` | `forward-word` | Forward one word |

## Editing

| Key         | Widget                 | Action                                   |
| ----------- | ---------------------- | ---------------------------------------- |
| `^D`        | `delete-char-or-list`  | Delete char (or list completions at EOL) |
| `^H` / `^?` | `backward-delete-char` | Backspace                                |
| `^W`        | `backward-kill-word`   | Kill word backward                       |
| `M-d`       | `kill-word`            | Kill word forward                        |
| `^K`        | `kill-line`            | Kill to end of line                      |
| `^U`        | `kill-whole-line`      | Kill entire line                         |
| `^Y`        | `yank`                 | Paste killed text                        |
| `M-y`       | `yank-pop`             | Cycle through kill ring                  |
| `^T`        | `transpose-chars`      | Swap chars                               |
| `M-t`       | `transpose-words`      | Swap words                               |
| `M-u`       | `up-case-word`         | UPPERCASE word                           |
| `M-l`       | `down-case-word`       | lowercase word                           |
| `M-c`       | `capitalize-word`      | Capitalize word                          |

## History

| Key | Widget | Action |
|-----|--------|--------|
| `^P` | `up-line-or-history` | Previous history |
| `^N` | `down-line-or-history` | Next history |
| `^R` | `history-incremental-search-backward` | Reverse search |
| `^S` | `history-incremental-search-forward` | Forward search |
| `M-.` | `insert-last-word` | Insert last word from previous line |

## Completion

| Key | Widget | Action |
|-----|--------|--------|
| `TAB` | `expand-or-complete` | Complete |
| `M-^D` | `list-choices` | List completions |

## Misc

| Key | Widget | Action |
|-----|--------|--------|
| `^L` | `clear-screen` | Clear screen |
| `^G` | `send-break` | Abort |
| `^V` | `quoted-insert` | Insert next char literally |
| `^X^E` | `edit-command-line` | Edit in $EDITOR (requires autoload) |

`^` = Ctrl, `M-` = Alt (or Esc prefix)