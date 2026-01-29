#todo

- Best editor in pracitce as degrades well and most portable.
	- If you know the terminal stack you can debug a broken server for example. You don't get this with [[VsCode]] or [[Jetbrains]]
	- Has a better modal editing system too.

Have a look at vimgolf
Repeat substitution is with ampersand

Addition and subtraction c-a and c-x (also nfformats option )

C o for insert normal mode 

C r and c p (register) to insert theb fix any indentation issues.

Should I remap the caps lock key?

C h delete one char
C w delete word
C u delete line.

C g for select mode

gv to select previous selections 

v /V / C v is visual mode goes back to normal mode

U Visiam mode uppercase l
### Not anki from here

Common commands:

Jump between misspellings:

]s   " next
[s   " previous


Suggestions for the word under cursor:

z=


Mark a word as correct:

zg   " add to personal dictionary
zw   " mark as wrong


Personal words are stored in a .add file (typically in ~/.config/nvim/spell/).

In **vimdiff**, if you want to **take (“obtain”) the entire highlighted difference**, use the diff commands:

### Take the change from the other window

* **From the other buffer into the current one**

  ```
  :diffget
  ```

  or shorthand:

  ```
  :dg
  ```

* **Put the current change into the other buffer**

  ```
  :diffput
  ```

  or shorthand:

  ```
  :dp
  ```

### For the *entire highlighted diff block*

1. Move the cursor anywhere inside the highlighted diff.
2. Run:

   ```
   :diffget
   ```

   Vim applies the **whole diff hunk**, not just the current line.

### With explicit window numbers

If you want to be precise about the source:

```
:diffget 2
```

(take from window 2 into the current window)

You can check window numbers with:

```
:ls
```

### Common mappings (if enabled)

Some setups provide:

* `do` → `:diffget`
* `dp` → `:diffput`

These also operate on the **entire diff hunk**, not a partial selection.

If you meant *selecting* multiple hunks or automating this across a file, say so and I’ll give the exact commands.


READ THIS!!!

https://lazyvim-ambitious-devs.phillips.codes/

Need to look at getting a start page with recently used files.

- `vim +42 filename` opens filename at line 42 
## Legend

* **READ**: worth reading end to end
* **SKIM**: read once quickly, come back if needed
* **REF**: keep as reference, do not read front to back
* **DATED**: mostly obsolete in a modern Neovim workflow

## Getting Started

* [x] usr_07.txt Editing more than one file (READ)

  * [x] 07.1 Edit another file (READ)
  * [x] 07.2 A list of files (READ)
  * [x] 07.3 Jumping from file to file (READ)
  * [x] 07.4 Backup files (SKIM)
  * [x] 07.5 Copy text between files (READ)
  * [x] 07.6 Viewing a file (SKIM)
  * [x] 07.7 Changing the file name (SKIM)

* [ ] usr_08.txt Splitting windows (READ)

  * [x] 08.1 Split a window (READ)
  * [x] 08.2 Split a window on another file (READ)
  * [x] 08.3 Window size (READ)
  * [x] 08.4 Vertical splits (READ)
  * [x] 08.5 Moving windows (READ)
  * [x] 08.6 Commands for all windows (READ)
  * [x] 08.7 Diff mode (READ)
  * [x] 08.8 Various (SKIM/REF)

* [x] usr_09.txt Using the GUI (DATED)

  * [ ] 09.1 Parts of the GUI (DATED)
  * [ ] 09.2 Using the mouse (SKIM)
  * [ ] 09.3 The clipboard (READ)
  * [ ] 09.4 Select mode (DATED)

* [x] usr_10.txt Making big changes (READ)

  * [ ] 10.1 Record and playback commands (READ)
  * [ ] 10.2 Substitution (READ)
  * [ ] 10.3 Command ranges (READ)
  * [ ] 10.4 The global command (READ)
  * [ ] 10.5 Visual block mode (READ)
  * [ ] 10.6 Reading and writing part of a file (SKIM)
  * [ ] 10.7 Formatting text (SKIM)
  * [ ] 10.8 Changing case (SKIM)
  * [ ] 10.9 Using an external program (REF)

* [ ] usr_11.txt Recovering from a crash (READ)

  * [ ] 11.1 Basic recovery (READ)
  * [ ] 11.2 Where is the swap file? (READ)
  * [ ] 11.3 Crashed or not? (SKIM)
  * [ ] 11.4 Further reading (REF)

* [ ] usr_12.txt Clever tricks (SKIM)

  * [ ] 12.1 Replace a word (SKIM)
  * [ ] 12.2 Reformat “Last, First” (SKIM)
  * [ ] 12.3 Sort a list (READ)
  * [ ] 12.4 Reverse line order (SKIM)
  * [ ] 12.5 Count words (SKIM)
  * [ ] 12.6 Find a man page (READ)
  * [ ] 12.7 Trim blanks (READ)
  * [ ] 12.8 Find where a word is used (READ)

## Editing Effectively

* [ ] usr_20.txt Typing command-line commands quickly (READ)

  * [ ] 20.1 Command line editing (READ)
  * [ ] 20.2 Command line abbreviations (SKIM)
  * [ ] 20.3 Command line completion (READ)
  * [ ] 20.4 Command line history (READ)
  * [ ] 20.5 Command line window (READ)

* [ ] usr_21.txt Go away and come back (READ)

  * [ ] 21.1 Suspend and resume (SKIM)
  * [ ] 21.2 Executing shell commands (READ)
  * [ ] 21.3 Remembering information; ShaDa (READ)
  * [ ] 21.4 Sessions (READ)
  * [ ] 21.5 Views (SKIM/REF)
  * [ ] 21.6 Modelines (READ)

* [ ] usr_22.txt Finding the file to edit (READ)

  * [ ] 22.1 File explorer (SKIM)
  * [ ] 22.2 The current directory (READ)
  * [ ] 22.3 Finding a file (READ)
  * [ ] 22.4 The buffer list (READ)

* [ ] usr_23.txt Editing other files (SKIM)

  * [ ] 23.1 DOS, Mac and Unix files (READ)
  * [ ] 23.2 Files on the internet (DATED)
  * [ ] 23.3 Binary files (REF)
  * [ ] 23.4 Compressed files (REF)

* [ ] usr_24.txt Inserting quickly (READ)

  * [ ] 24.1 Making corrections (READ)
  * [ ] 24.2 Showing matches (SKIM)
  * [ ] 24.3 Completion (READ)
  * [ ] 24.4 Repeating an insert (READ)
  * [ ] 24.5 Copying from another line (READ)
  * [ ] 24.6 Inserting a register (READ)
  * [ ] 24.7 Abbreviations (SKIM)
  * [ ] 24.8 Entering special characters (REF)
  * [ ] 24.9 Digraphs (DATED/REF)
  * [ ] 24.10 Normal mode commands (READ)

* [ ] usr_25.txt Editing formatted text (READ)

  * [ ] 25.1 Breaking lines (READ)
  * [ ] 25.2 Aligning text (READ)
  * [ ] 25.3 Indents and tabs (READ)
  * [ ] 25.4 Dealing with long lines (READ)
  * [ ] 25.5 Editing tables (SKIM)

* [ ] usr_26.txt Repeating (READ)

  * [ ] 26.1 Repeat with Visual mode (READ)
  * [ ] 26.2 Add and subtract (READ)
  * [ ] 26.3 Make a change in many files (READ)
  * [ ] 26.4 Using Vim from a shell script (REF)

* [ ] usr_27.txt Search commands and patterns (READ)

  * [ ] 27.1 Ignoring case (READ)
  * [ ] 27.2 Wrapping around the end of the file (SKIM)
  * [ ] 27.3 Offsets (READ)
  * [ ] 27.4 Matching multiple times (READ)
  * [ ] 27.5 Alternatives (READ)
  * [ ] 27.6 Character ranges (READ)
  * [ ] 27.7 Character classes (READ)
  * [ ] 27.8 Matching a line break (READ)
  * [ ] 27.9 Examples (READ)

* [ ] usr_28.txt Folding (READ)

  * [ ] 28.1 What is folding? (READ)
  * [ ] 28.2 Manual folding (SKIM)
  * [ ] 28.3 Working with folds (READ)
  * [ ] 28.4 Saving and restoring folds (READ)
  * [ ] 28.5 Folding by indent (READ)
  * [ ] 28.6 Folding with markers (SKIM)
  * [ ] 28.7 Folding by syntax (SKIM)
  * [ ] 28.8 Folding by expression (REF)
  * [ ] 28.9 Folding unchanged lines (REF)
  * [ ] 28.10 Which fold method? (READ)

* [ ] usr_29.txt Moving through programs (READ)

  * [ ] 29.1 Using tags (SKIM)
  * [ ] 29.2 The preview window (READ)
  * [ ] 29.3 Moving through a program (READ)
  * [ ] 29.4 Finding global identifiers (READ)
  * [ ] 29.5 Finding local identifiers (READ)

* [ ] usr_30.txt Editing programs (READ)

  * [ ] 30.1 Compiling (SKIM)
  * [ ] 30.2 Indenting C files (DATED)
  * [ ] 30.3 Automatic indenting (READ)
  * [ ] 30.4 Other indenting (READ)
  * [ ] 30.5 Tabs and spaces (READ)
  * [ ] 30.6 Formatting comments (READ)

* [ ] usr_31.txt Exploiting the GUI (DATED)

  * [ ] 31.1 The file browser (DATED)
  * [ ] 31.2 Confirmation (SKIM)
  * [ ] 31.3 Menu shortcuts (DATED)
  * [ ] 31.4 Window position and size (DATED)
  * [ ] 31.5 Various (DATED/REF)

* [ ] usr_32.txt The undo tree (READ)

  * [ ] 32.1 Undo up to a file write (READ)
  * [ ] 32.2 Numbering changes (SKIM)
  * [ ] 32.3 Jumping around the tree (READ)
  * [ ] 32.4 Time travelling (READ)

## Tuning Neovim

* [ ] usr_40.txt Make new commands (READ)

  * [ ] 40.1 Key mapping (READ)
  * [ ] 40.2 Defining command-line commands (READ)
  * [ ] 40.3 Autocommands (READ)

* [ ] usr_41.txt Write a Vim script (REF)

  * [ ] 41.1 Introduction (SKIM)
  * [ ] 41.2 Variables (REF)
  * [ ] 41.3 Expressions (REF)
  * [ ] 41.4 Conditionals (REF)
  * [ ] 41.5 Executing an expression (REF)
  * [ ] 41.6 Functions (REF)
  * [ ] 41.7 Defining a function (REF)
  * [ ] 41.8 Lists and Dictionaries (REF)
  * [ ] 41.9 Exceptions (REF)
  * [ ] 41.10 Various remarks (REF)
  * [ ] 41.11 Writing a plugin (SKIM/REF)
  * [ ] 41.12 Writing a filetype plugin (READ)
  * [ ] 41.13 Writing a compiler plugin (REF)
  * [ ] 41.14 Writing plugins quickly (READ)
  * [ ] 41.15 Writing library scripts (REF)
  * [ ] 41.16 Distributing Vim scripts (REF)

* [ ] usr_42.txt Add new menus (DATED)

  * [ ] 42.1 Introduction (DATED)
  * [ ] 42.2 Menu commands (DATED)
  * [ ] 42.3 Various (DATED)
  * [ ] 42.4 Toolbar and popup menus (DATED)

* [ ] usr_43.txt Using filetypes (READ)

  * [ ] 43.1 Using filetype plugins (READ)
  * [ ] 43.2 Adding a filetype (READ)

* [ ] usr_44.txt Your own syntax highlighted (REF)

  * [ ] 44.1 Basic syntax commands (REF)
  * [ ] 44.2 Keywords (REF)
  * [ ] 44.3 Matches (REF)
  * [ ] 44.4 Regions (REF)
  * [ ] 44.5 Nested items (REF)
  * [ ] 44.6 Following groups (REF)
  * [ ] 44.7 Other arguments (REF)
  * [ ] 44.8 Clusters (REF)
  * [ ] 44.9 Including another syntax file (REF)
  * [ ] 44.10 Synchronizing (REF)
  * [ ] 44.11 Installing a syntax file (REF)
  * [ ] 44.12 Portable layout (REF)

* [ ] usr_45.txt Select your language (locale) (SKIM/REF)

  * [ ] 45.1 Language for messages (DATED/REF)
  * [ ] 45.2 Language for menus (DATED)
  * [ ] 45.3 Using another encoding (READ)
  * [ ] 45.4 Editing files with another encoding (READ)
  * [ ] 45.5 Entering language text (SKIM/REF)

---

## Neovim help index checklist

### Nvim documentation
- [x] nvim-intro (READ)
- [ ] Q_ct About Nvim (REF)
- [ ] news News since the previous release (SKIM/REF)
- [ ] nvim Getting started with Nvim (READ)
- [ ] tutor 30-minute interactive course (READ)
- [ ] vim-differences Nvim compared to Vim (SKIM)
- [ ] faq Frequently Asked Questions (SKIM)
- [ ] tips Various tips (REF)
- [ ] bugs Where to send bug reports (REF)
- [ ] support Supported platforms (REF)
- [ ] copying About copyrights (DATED/REF)

### Usage
- [ ] helphelp Using the :help files (READ)
- [ ] intro Introduction to Vim (SKIM)
- [ ] quickref Overview of common commands (READ)
- [ ] index Index of all commands (REF)
- [ ] user-manual User manual (READ)  
  - Note: covered above via usr_01..usr_45 checklist
- [ ] message.txt (Error) messages and explanations (REF)
- [ ] Kuwasha Helping poor children in Uganda (DATED/OPTIONAL)

### Basic editing
- [ ] starting Starting Vim, arguments, initialisation (READ)
- [ ] edit-files Editing and writing files (READ)
- [ ] motion.txt Moving around (READ)
- [ ] scrolling Scrolling the text in the window (READ)
- [ ] insert.txt Insert and Replace mode (READ)
- [ ] change.txt Deleting and replacing text (READ)
- [ ] undo-redo Undo and Redo (READ)
- [ ] repeat.txt Repeating commands, Vim scripts and debugging (READ)
- [ ] visual-mode Using Visual mode (READ)
- [ ] various Various other commands (SKIM)
- [ ] crash-recovery Recovering from a crash (READ)

### Advanced editing
- [ ] cmdline Command-line editing (READ)
- [ ] options Description of all options (REF)
- [ ] pattern-searches Regexp patterns and search commands (READ)
- [ ] key-mapping Key mapping, abbreviations (READ)
- [ ] tags Tags and special searches (SKIM)
- [ ] windows Windows and buffers (READ)
- [ ] tabpage Tabpages (SKIM)
- [ ] spell Spell checking (SKIM)
- [ ] diff Comparing files (READ)
- [ ] folding Fold ranges of lines (READ)
- [ ] terminal Embedded terminal emulator (READ)

### API (extensibility, scripting, plugins)
- [ ] api Nvim API via RPC, Lua and Vimscript (READ)
- [ ] ui Nvim UI protocol (REF)
- [ ] lua-guide Nvim Lua guide (READ)
- [ ] lua Lua API (REF)
- [ ] luaref Lua reference manual (REF)
- [ ] luvref Luv (vim.uv) reference manual (REF)
- [ ] autocmd Event handlers (READ)
- [ ] job-control Spawn and control processes (REF)
- [ ] channel Nvim asynchronous IO (REF)
- [ ] vimscript Vimscript reference (REF)
- [ ] vimscript-functions Vimscript functions (REF)
- [ ] remote-plugin Nvim remote plugins (REF)
- [ ] health Health checking (READ)

### Programming language support
- [ ] lsp Language Server Protocol (READ)
- [ ] diagnostic-api Diagnostic framework (REF)
- [ ] treesitter Incremental syntax parsing (READ)
- [ ] indent.txt Automatic indenting for C and other languages (SKIM)
- [ ] syntax Syntax highlighting (SKIM/REF)
- [ ] filetype Settings for specific types of files (READ)
- [ ] quickfix Quick edit-compile-fix cycle (READ)
- [ ] ft_ada.txt Ada filetype plugin (REF)
- [ ] ft_hare.txt Hare filetype plugin (REF)
- [ ] ft_ps1.txt PowerShell filetype plugin (REF)
- [ ] ft_raku.txt Raku filetype plugin (REF)
- [ ] ft_rust.txt Rust filetype plugin (REF)
- [ ] ft_sql.txt SQL filetype plugin (REF)

### UI
- [ ] tui Built-in UI (SKIM)
- [ ] gui External graphical UIs (SKIM/REF)
- [ ] signs Signs in the gutter (SKIM)

### Multilingual support
- [ ] digraph List of available digraphs (REF)
- [ ] mbyte.txt Multibyte text support (REF)
- [ ] mlang.txt Non-English language support (REF)
- [ ] rileft.txt Right-to-left editing mode (REF)
- [ ] l10n-arabic.txt Arabic support (REF)
- [ ] l10n-hebrew.txt Hebrew support (REF)
- [ ] l10n-russian.txt Russian support (REF)
- [ ] l10n-vietnamese.txt Vietnamese support (REF)

### Interop
- [ ] provider Builtin remote plugin hosts (READ)
- [ ] if_perl Perl interface (DATED/REF)
- [ ] if_pyth Python interface (SKIM/REF)
- [ ] if_ruby Ruby interface (DATED/REF)

### Versions
- [ ] deprecated Deprecated features (READ)
- [ ] vi-differences Differences between Vim and Vi (SKIM)

### Developing nvim
- [ ] dev Development of Nvim (SKIM)
- [ ] dev-arch Internal architecture (REF)
- [ ] dev-style Development style guidelines (REF)
- [ ] dev-test Writing and running tests (REF)
- [ ] dev-theme Design guidelines (REF)
- [ ] dev-tools Tools and techniques for developing Nvim (REF)
- [ ] dev-vimpatch Merging patches from Vim (REF)

### Standard plugins
- [ ] standard-plugin-list (REF)

### Local additions
- [ ] bars Bars example (DATED/OPTIONAL)

## Suggested order for these help topics
- [ ] Phase A: nvim-intro, tutor, helphelp, quickref
- [ ] Phase B: starting, edit-files, motion.txt, insert.txt, change.txt, undo-redo, repeat.txt, visual-mode
- [ ] Phase C: cmdline, pattern-searches, windows, diff, terminal
- [ ] Phase D: lua-guide, autocmd, api, health, lsp, treesitter
- [ ] Phase E: Everything marked REF or DATED as needed

usr_07 (Multiple files) - Major gaps:

    :next / :previous / :wnext / :wprevious
    :first / :last
    :args (show argument list)
    :set autowrite
    :file {name} (rename current buffer)
    :set backup / :set backupext / :set patchmode
    Appending to registers with uppercase ("Ayy)
    :write >> {file} (append to file)

usr_08 (Windows) - Substantial gaps:

    :only (close all other windows)
    :new / :vnew
    :vertical {cmd} modifier
    CTRL-W + / CTRL-W - (resize)
    {height}CTRL-W _ (set window height)
    CTRL-W t / CTRL-W b (top/bottom window)
    CTRL-W H/J/K/L (move window to edge)
    :qall / :wall / :wqall / :qall!
    vim -o / vim -O (start with splits)
    vimdiff: :diffsplit, ]c/[c, dp/do
    zo / zc (open/close fold)
    :set splitbelow / :set splitright
    CTRL-W CTRL-^ (split + alternate file)


## Plugin ideas

- [[Obsidian]] plugin for Neovim.
