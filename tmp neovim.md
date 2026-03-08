
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

- `<F1>` opens the netrw help page; use `Ctrl-]` to jump to help tags and `Ctrl-o` to jump back.
- Open file: `o` (horizontal split), `v` (vertical split), `p` (preview), `P` (previous window), `t` (new tab).
- `i` cycles listing styles (thin/long/wide/tree).
- `s` cycles sort keys (name/mtime/size); `r` reverses sort order.
- `cd` sets Vim's current directory to the browser directory.
- `R` renames; `D` deletes; `mb`/`gb` make/goto bookmark.
- `:Explore [dir]` opens netrw; `:NetrwSettings` lists netrw settings with help links.
- Remote browsing: `:Explore ftp://host/path/` or `:e scp://host/path/` (trailing `/` matters).

## Current directory

- Change global current directory: `:cd {dir}`.
- Jump to previous directory: `:cd -`.
- Window-local directories (via `:lcd`) override the global dir; windows without one share the global dir.
- If a window has a local dir, running `:cd` there returns it to the shared global dir.
- Tab-local directory: `:tcd {dir}`; applies to all windows in the tab except those with a local dir.
- New tabs inherit the directory from the window they were opened from.
- `:cd` does not change other tabs that have a tab-local directory.

## Finding a file

- `gf` edits the file name under the cursor.
- If the file is not in the current directory, `gf` searches using the `'path'` option.
- `Ctrl-w f` opens the file under the cursor in a new window.
- `:sfind` searches like `:find` but opens the result in a split.
- `'isfname'` controls which characters are considered part of a filename.

## Hidden buffers

- `:hide {cmd}` runs a command as if `'hidden'` were set, allowing you to leave a modified buffer without writing it.
- Example: `:hide edit two.txt` keeps changes in `one.txt` but switches to `two.txt`.
- Setting `'hidden'` makes any abandoned buffer become hidden.
- If you have hidden modified buffers, ensure you save them before exiting Vim.

## Inactive buffers

- Active buffer: displayed in a window; text loaded.
- Hidden buffer: not displayed; text loaded.
- Inactive buffer: not displayed; text not loaded.
- Inactive buffers remain in the buffer list with info like marks and filenames.
- List buffers: `:buffers`.
- Buffer name matching: when you type a buffer name (e.g., with `:buffer`/`:b`), Vim picks the best match; a unique match is used.
- Open a buffer in a new window: `:sbuffer {bufnr|name}`.
- Remove buffer from the list: `:bdelete {bufnr|name}`.
- Deleting an active/current buffer closes its window; if it was the last window, Vim opens another buffer.
- `:bdelete` makes a buffer unlisted (hidden from `:buffers`); `:buffers!` shows unlisted buffers.
- To fully forget a buffer, use `:bwipe` (see `'buflisted'`).


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



:pwd
/home/Bram/VeryLongFileName


INACTIVE BUFFERS

   When a buffer has been used once, Vim remembers some information about it.
When it is not displayed in a window and it is not hidden, it is still in the
buffer list.  This is called an inactive buffer.  Overview:

   Active		Appears in a window, text loaded.
   Hidden		Not in a window, text loaded.
   Inactive		Not in a window, no text loaded.

The inactive buffers are remembered, because Vim keeps information about them,
like marks.  And remembering the file name is useful too, so that you can see
which files you have edited.  And edit them again.

A command which does the same, is not so obvious to list buffers, but is much
shorter to type: >

	:ls

The output could look like this:

  1 #h   "help.txt"			line 62 ~
  2 %a + "usr_21.txt"			line 1 ~
  3      "usr_toc.txt"			line 1 ~

The first column contains the buffer number.  You can use this to edit the
buffer without having to type the name, see below.
   After the buffer number come the flags.  Then the name of the file
and the line number where the cursor was the last time.
   The flags that can appear are these (from left to right):

	u	Buffer is unlisted |unlisted-buffer|.
	 %	Current buffer.
	 #	Alternate buffer.
	  a	Buffer is loaded and displayed.
	  h	Buffer is loaded but hidden.
	   =	Buffer is read-only.
	   -	Buffer is not modifiable, the 'modifiable' option is off.
	    +	Buffer has been modified.


2. Special special keys				*ins-special-special*

The following keys are special.  They stop the current insert, do something,
and then restart insertion.  This means you can do something without getting
out of Insert mode.  This is very handy if you prefer to use the Insert mode
all the time, just like editors that don't have a separate Normal mode. You
can use CTRL-O if you want to map a function key to a command.

The changes (inserted or deleted characters) before and after these keys can
be undone separately.  Only the last change can be redone and always behaves
like an "i" command.

char		action	~
-----------------------------------------------------------------------
<Up>		cursor one line up			     *i_<Up>*
<Down>		cursor one line down			     *i_<Down>*
CTRL-G <Up>	cursor one line up, insert start column	     *i_CTRL-G_<Up>*
CTRL-G k	cursor one line up, insert start column	     *i_CTRL-G_k*
CTRL-G CTRL-K	cursor one line up, insert start column	     *i_CTRL-G_CTRL-K*
CTRL-G <Down>	cursor one line down, insert start column    *i_CTRL-G_<Down>*
CTRL-G j	cursor one line down, insert start column    *i_CTRL-G_j*
CTRL-G CTRL-J	cursor one line down, insert start column    *i_CTRL-G_CTRL-J*
<Left>		cursor one character left		     *i_<Left>*
<Right>		cursor one character right		     *i_<Right>*
<S-Left>	cursor one word back (like "b" command)	     *i_<S-Left>*
<C-Left>	cursor one word back (like "b" command)	     *i_<C-Left>*
<S-Right>	cursor one word forward (like "w" command)   *i_<S-Right>*
<C-Right>	cursor one word forward (like "w" command)   *i_<C-Right>*
<Home>		cursor to first char in the line	     *i_<Home>*
<End>		cursor to after last char in the line	     *i_<End>*
<C-Home>	cursor to first char in the file	     *i_<C-Home>*
<C-End>		cursor to after last char in the file	     *i_<C-End>*
<LeftMouse>	cursor to position of mouse click	     *i_<LeftMouse>*
<S-Up>		move window one page up			     *i_<S-Up>*
<PageUp>	move window one page up			     *i_<PageUp>*
<S-Down>	move window one page down		     *i_<S-Down>*
<PageDown>	move window one page down		     *i_<PageDown>*
<ScrollWheelDown>    move window three lines down	*i_<ScrollWheelDown>*
<S-ScrollWheelDown>  move window one page down		*i_<S-ScrollWheelDown>*
<ScrollWheelUp>      move window three lines up		*i_<ScrollWheelUp>*
<S-ScrollWheelUp>    move window one page up		*i_<S-ScrollWheelUp>*
<ScrollWheelLeft>    move window six columns left	*i_<ScrollWheelLeft>*
<S-ScrollWheelLeft>  move window one page left		*i_<S-ScrollWheelLeft>*
<ScrollWheelRight>   move window six columns right	*i_<ScrollWheelRight>*
<S-ScrollWheelRight> move window one page right		*i_<S-ScrollWheelRight>*
CTRL-O		execute one command, return to Insert mode   *i_CTRL-O*
CTRL-\ CTRL-O	like CTRL-O but don't move the cursor	     *i_CTRL-\_CTRL-O*
CTRL-G u	close undo sequence, start new change	     *i_CTRL-G_u*
CTRL-G U	don't start a new undo block with the next   *i_CTRL-G_U*
		left/right cursor movement, if the cursor
		stays within the same line



*24.2*	Showing matches

When you type a ) it would be nice to see with which ( it matches.  To make
Vim do that use this command: >

	:set showmatch

When you now type a text like "(example)", as soon as you type the ) Vim will
briefly move the cursor to the matching (, keep it there for half a second,
and move back to where you were typing.
   In case there is no matching (, Vim will beep.  Then you know that you
might have forgotten the ( somewhere, or typed a ) too many.
   The match will also be shown for [] and {} pairs.  You don't have to wait
with typing the next character, as soon as Vim sees it the cursor will move
back and inserting continues as before.
   You can change the time Vim waits with the 'matchtime' option.  For
example, to make Vim wait one and a half second: >

	:set matchtime=15

