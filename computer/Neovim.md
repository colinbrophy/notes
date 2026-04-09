#todo

- [ ] List all the plugins we need to review in [[Neovim Plugins]]
- [ 
- [ ] Learn [[Netrw]]
- [ ] https://github.com/github/copilot.vim

- Best editor in pracitce as degrades well and most portable.
	- If you know the terminal stack you can debug a broken server for example. You don't get this with [[VsCode]] or [[Jetbrains]]
	- Has a better modal editing system too.

Have a look at vimgolf
Repeat substitution is with ampersand

Caps.lock key

Try to use ctrl o more

Try to use `.` a bit more, you don't use it enough.

Consider:

Commentary
Textobj-entire


READ THIS!!!

https://lazyvim-ambitious-devs.phillips.codes/

Need to look at getting a start page with recently used files.

- `vim +42 filename` opens filename at line 42 
## Legend

* **READ**: worth reading end to end
* **SKIM**: read once quickly, come back if needed
* **REF**: keep as reference, do not read front to back
* **DATED**: mostly obsolete in a modern Neovim workflow


* [ ] usr_31.txt Exploiting the GUI (DATED)

  * [ ] 31.1 The file browser (DATED)
  * [ ] 31.2 Confirmation (SKIM)
  * [ ] 31.3 Menu shortcuts (DATED)
  * [ ] 31.4 Window position and size (DATED)
  * [ ] 31.5 Various (DATED/REF)

* [x] usr_32.txt The undo tree (READ)

## Tuning Neovim

* [ ] usr_40.txt Make new commands (READ)

  * [ ] 40.1 Key mapping (READ)
  * [ ] 40.2 Defining command-line commands (READ)
  * [ ] 40.3 Autocommands (READ)

* [ ] usr_43.txt Using filetypes (READ)
  * [ ] 43.1 Using filetype plugins (READ)
  * [ ] 43.2 Adding a filetype (READ)

## Neovim help index checklist

### Nvim documentation
- [x] nvim-intro (READ)
- [ ] Q_ct About Nvim (REF)
- [ ] news News since the previous release (SKIM/REF)
- [ ] nvim Getting started with Nvim (READ)
- [x] tutor 30-minute interactive course (READ)
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
- [x] user-manual User manual (READ)  
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

## Plugin ideas

- [[Obsidian]] plugin for Neovim.
