
**						*'wrapmargin'* *'wm'*
'wrapmargin' 'wm'	number	(default 0)
			local to buffer
	Number of characters from the right window border where wrapping
	starts.  When typing text beyond this limit, an <EOL> will be inserted
	and inserting continues on the next line.
	Options that add a margin, such as 'number' and 'foldcolumn', cause
	the text width to be further reduced.
	When 'textwidth' is non-zero, this option is not used.
	See also 'formatoptions' and |ins-textwidth|.


# next for anki cards\


Copy command create cards :t

Move command :m

Normally :normal

@: to repeat 

C r c w and c r c a

q: and <CR> and c f , q/

Current file name %

:she'll

:write ! Vs :write!

:[range]!

% symbol on the buffer list and plus sign 

First and blast

:b [number or name]

:bufdo

Bd [number or name of buffer]

:Args with backpacks for commands


C w c and C w o

C w|

C w t

:lcd

{N}Gt gt gT

Tabnext tabprevious

Tabmove

# next anki cards

:pwd
:edit %:h

:find 

:set path
Set wildmode
# netrw

Enter to enter dir file

- to move up


pow()

## Command line editing

- Command line shows at the bottom for `:` commands and `/` or `?` searches.
- You can edit in place; no need to move to the end before `<Enter>`.
- Cursor movement: `<Left>`/`<Right>` (char), `<S-Left>` or `<C-Left>` (word left), `<S-Right>` or `<C-Right>` (word right), `Ctrl-b` or `<Home>` (start), `Ctrl-e` or `<End>` (end).
- Note: Shift/Ctrl cursor combos do not work on all keyboards.
- Mouse can move the command-line cursor.

```text
:s/col/pig/
<Left> x5, <BS>, w
:s/cow/pig/
```

## Deleting (command line)

- `<BS>` deletes the previous character.
- `Ctrl-w` deletes the previous word.
- `Ctrl-u` clears the whole command line.

```text
/the fine pig
Ctrl-w
/the fine
```

## Overstrike (command line)

- `<Insert>` toggles insert vs overstrike.
- Overstrike replaces existing characters and can eat spaces; toggle back to insert to add missing spaces.

```text
/the fine pig
<Insert>, type "great" -> /the greatpig
<Insert>, add space -> /the great pig
```

## Cancelling (command line)

- `Ctrl-c` or `<Esc>` cancels without executing.
- At the start of the line, `<BS>` cancels (deletes the leading `:` or `/`).

## Command line completion

- `<Tab>` completes the word before the cursor. With multiple matches, Vim beeps and inserts the first match; repeat `<Tab>` to cycle forward and eventually return to what you typed.
- `Ctrl-p` cycles backward through the match list.
- Completion is context sensitive (e.g., `:set i<Tab>` completes an option like `icon`, not a file).
- Type more characters to narrow matches (`:set isk<Tab>` -> `:set iskeyword`).
- After `=` in `:set iskeyword=`, completion inserts the current value so you can edit it.
- If completion is not implemented for that spot, Vim inserts a literal tab (`^I`).

## Command line history

- `<Up>` and `<Down>` recall older/newer entries.
- Histories: `:` commands, `/` + `?` search commands (shared), plus expression, debug, and input() histories.
- Prefix filtering: typing `:se<Up>` jumps to the previous history entry starting with `se`.
- If you miss it, use `<Down>` to return to what you typed and edit, or `Ctrl-u` to clear.
- List history: `:history` (colon commands), `:history /` (search history).
- `Ctrl-p`/`Ctrl-n` move through history regardless of what you've typed so far.

## Command line window

- Open with `q:` to edit command-line history in a window.
- You are in Normal mode; use `hjkl` to move and edits stay in the window.
- `<Enter>` executes the line under the cursor (works from Normal or Insert mode).
- Edits in this window do not change history; only the executed command is added.
- Use `/` or `?` to search inside the command line window.
- Only one command line window at a time; you cannot open another while in it.

## ShaDa (shared data)

- ShaDa stores command-line and search history, registers, marks, buffer list, and global variables.
- Written on exit and read on startup; the last Vim to exit wins.
- Configure with `:set shada=...` using comma-separated option+arg pairs.

```text
:set shada='1000,f1,<500
```

- Useful options: `'` (file marks count), `f` (store global marks), `<` (lines per register), `:` (cmdline history), `@` (input-line history), `/` (search history), `r` (no marks on removable media), `!` (uppercase global vars), `h` (disable hlsearch on start), `%` (buffer list), `c` (convert encoding), `n` (shada filename, must be last).

## Return to where you left

- On exit, Vim sets mark `'0` to the last position; previous marks shift to `'1`..`'9`.
- Jump back with `'0`; see them with `:marks`.

## Old files list

- Show recent files: `:oldfiles`.
- Edit by index: `:e #<2` (works anywhere a filename is accepted), or `:split #<3`.
- Interactive picker: `:browse oldfiles` then enter the index.

## Move ShaDa between Vims

- Write ShaDa: `:wshada! /tmp/shada` (force overwrite with `!`).
- Read ShaDa: `:rshada! /tmp/shada` (file wins with `!`; without `!`, only unset info is used).

## Sessions

- Save session: `:mksession vimbook.vim`.
- Restore: `:source vimbook.vim` or start with `vim -S vimbook.vim`.
- Control what is saved with `sessionoptions` (default: `blank,buffers,curdir,folds,help,options,tabpages,winsize,terminal`).
- Include Vim window size with `:set sessionoptions+=resize`.

## Views

- A view stores window-local state for a single file (options like `number`, folds, cursor, etc.).
- Store current view: `:mkview`. Restore for the same file: `:loadview`.
- Numbered views: `:mkview 1` and `:loadview 1` (up to 1–9 plus the unnumbered view).
- Named view file: `:mkview ~/.config/nvim/main.vim`, restore with `:source ~/.config/nvim/main.vim` (can jump to that file).
