# Command Triage

## Active inventory

### Git
- [ ] `git`: version control
  - [ ] Standalone developer workflow
    - [ ] `git config`: inspect/set identity, defaults, aliases, and tool integration
    - [x] `git init`: create a new repository
    - [x] `git log`: see what happened
    - [ ] `git show`: inspect one commit, tag, or object
    - [ ] `git reflog`: recover where branches/HEAD used to point
    - [x] `git switch`
    - [x] `git branch`: switch and manage branches
    - [x] `git add`: manage the index/staging area
    - [x] `git diff`
    - [x] `git status`: see what you are in the middle of doing
    - [ ] `git commit`: advance the current branch
		- Got up to --fixup (learn rebase first)
    - [x] `git restore`: undo changes
    - [x] `git reset`: move HEAD/index and undo staged work
    - [x] `git clean`: remove untracked files/directories
    - [x] `git rm`, `git mv`: remove/rename tracked files
    - [x] `git stash`: park dirty work temporarily to 
    - [x] `git merge`: merge between local branches
	    - [ ] Come back to --cleanup=
    - [x] `git rebase`: maintain topic  branches
    - [x] `git cherry-pick`: apply syelected commits onto the current branch
    - [x] `git bisect`: find the commit that introduced a regression
    - [ ] `git blame`: trace which commit last changed lines
    - [x] `git grep`: search tracked files quickly
    - [x] `git tag`: mark a known point
  - [ ] Individual developer participant workflow
    - [x] `git clone`: prime a local repository from upstream
    - [x] `git remote`: inspect and manage upstream remotes
    - [ ] `git pull`, `git fetch`: keep up to date with upstream
		- Read the manual of `fetch` (partiualcly the refspec part) more carefully.
    - [ ] `git push`: publish to a shared repository
    - [ ] `git submodule`: manage nested external repositories when a project uses them
    - [ ] `git rev-parse`: scripting helper for repo roots, refs, and object names
  - [ ] Occasional but important Git workflows
    - [ ] `git mergetool`, `git difftool`: use external tools for conflicts and diffs
    - [ ] `git ls-files`: show files tracked by Git
    - [ ] `git describe`: derive human-readable version strings from tags and commits
    - [ ] `git filter-repo`: rewrite history for cleanup or secret removal; learn carefully when needed
    - [ ] `git archive`: export a clean tar/zip snapshot of tracked files at a commit
    - [ ] `git fsck`: check repository object integrity when diagnosing corruption
    - [ ] `git format-patch`, `git am`: email/patch-based contribution workflow
- [x] `git worktree`
- [ ] `gitrevisions`: Git revision/range syntax
- [ ] `gitignore`
- [ ] `githooks`

### GitHub and GitHub Actions
- [ ] `gh`: GitHub CLI
- [ ] `act`: run GitHub Actions locally
- [ ] `actionlint`: lint GitHub Actions workflows
- [ ] `zizmor`: audit GitHub Actions workflows for security problems

### Terraform
- [ ] `terraform`: core workflow (`fmt`, `validate`, `plan`, `apply`, `output`, `state`, `console`, `import`)
- [ ] `tflint` catches Terraform and provider-specific mistakes
- [ ] `tfsec` performs Terraform static security scanning
- [ ] `infracost` estimates Terraform/OpenTofu cloud costs
- [ ] `terraform-docs` generates documentation for Terraform modules
- [ ] `terraform-ls` is the Terraform language server

### AWS
- [ ] `aws`: AWS CLI
- [ ] `aws sts get-caller-identity`: fastest identity/account sanity check
- [ ] `aws sso login`: authenticate with AWS IAM Identity Center / SSO
- [ ] `aws configure sso`: initial SSO profile setup

### Ansible
- [ ] `ansible-playbook`: run playbooks

### PostgreSQL
- [ ] `psql`: PostgreSQL shell for inspection and admin
- [ ] `pg_isready` provides a fast PostgreSQL readiness/connectivity check
- [ ] `pg_dump`: logical backup of a PostgreSQL database
- [ ] `pg_restore`: restore `pg_dump` custom/directory backups
- [ ] `pg_dumpall` dumps all PostgreSQL databases plus global objects like roles
- [ ] `pg_basebackup` performs physical PostgreSQL and replication base backups
- [ ] `vacuumdb` runs vacuum/analyze/maintenance without opening `psql`
- [ ] `reindexdb` rebuilds indexes when debugging corruption or bloat issues
- [ ] `pgcli` is an enhanced PostgreSQL shell with completion and syntax highlighting
- [x] `createdb` creates a PostgreSQL database from the CLI
- [ ] `createuser` creates PostgreSQL roles/users from the CLI

### Terminal docs and browsing
- [ ] `w3m`: terminal web browser
- [ ] `glow`: terminal markdown renderer
- [ ] `cheat`: cheat sheets in terminal
- [ ] `tldr`: short, example-first command docs
- [ ] `cht.sh`: curlable cheat sheets / quick example
- [ ] `xdg-open`: open a file/URL with the desktop default app

### Shell basics
- [x] `bash`: your shell            
- [ ] `zsh`: alternative shell (learn line editing here)
- [x] `cd`: change directory
- [x] `pwd`: print working directory
- [x] `ls`: list files
- [x] `cp`: copy 
- [x] `mv`: move/rename
- [x] `rm`: remove
- [x] `rmdir`: remove empty dirs
- [x] `mkdir`: make dirs
- [x] `ln`: links (hard + symlinks)
- [x] `touch`: create/update timestamps
- [x] `cat`: concatenate/display files
- [x] `less`: pager
- [x] `head`: first N lines
- [x] `tail`: last N lines (tail -f for log following)
- [x] `echo`: print text
- [x] `printf`: formatted print
- [x] `read`: read input in scripts
- [x] `time`: measure how long a command takes
- [x] `test`: conditional evaluation ([ ])
- [x] `true`: exit 0
- [x] `false`: exit 1
- [x] `yes`: repeat string forever
- [x] `sleep`: delay for a fixed duration
- [x] `seq`: generate numeric sequences for loops, filenames, and quick test data

### Shell language / builtins
- [x] `type`: show whether something is a shell builtin, alias, function, or binary
- [x] `which`: locate a command in `PATH`; prefer `type` for shell-aware lookup
- [x] `help`: shell builtin docs
- [x] `command`: run command bypassing shell functions/aliases
- [x] `builtin`: run shell builtin explicitly
- [x] `alias`: define/list aliases
- [x] `unalias`: remove aliases
- [x] `export`: put variables into environment
- [x] `unset`: remove variable/function
- [x] `set`: shell options + positional parameters
- [x] `shopt`: Bash-specific shell options
- [x] `source`: run file in current shell
- [x] `.`: POSIX source
- [x] `pushd`: push the current directory onto the stack and switch directories
- [x] `popd`: pop a directory off the stack and switch back to it
- [x] `dirs`: show or manipulate the shell directory stack
- [x] `exec`: replace current shell/process
- [x] `trap`: handle signals/cleanup in scripts
- [x] `return`: return from function/sourced script
- [x] `exit`: exit shell/script
- [x] `shift`: shift positional parameters
- [ ] `getopts`: parse shell script flags
- [x] `ulimit`: shell resource limits
- [x] `history`: shell history
- [x] `fc`: edit/re-run previous commands
- [x] `bindkey`: zsh keybindings
- [x] `bind`: bash/readline keybindings
- [x] `declare`: set shell variables and attributes

### Text processing
- [x] `grep`: pattern search
- [x] `sed`: stream editor [Read this](https://www.grymoire.com/Unix/Sed.html)
- [x] `awk`: pattern/action language
	- [x] https://catonmat.net/awk-book
- [x] `sort`: sort lines
- [x] `uniq`: deduplicate adjacent lines
- [x] `wc`: word/line/byte count
- [x] `cut`: extract fields
- [x] `tr`: translate/delete characters
- [x] `tee`: split stdout to file + pipe
- [x] `stdbuf`: adjust stdio buffering in pipelines
- [x] `xargs`: build commands from stdin
- [x] `diff`: compare files
- [ ] `diff3`: three-way file comparison
- [x] `sdiff`: side-by-side diff
- [x] `patch`: apply diffs
- [ ] `comm`: compare sorted files line by line
	- [ ] We need -1,-2,3 as cards.
- [x] `paste`: merge lines side by side
- [x] `join`: join sorted text files on a shared field
- [x] `column`: format into columns
- [x] `numfmt`: convert numbers to/from human-readable units
- [x] `fold`: wrap lines
- [x] `fmt`: simple text formatter
- [x] `expand`: tabs to spaces
- [x] `unexpand`: spaces to tabs
- [x] `cmp`
- [x] `shuf`
- [x] `rev`: reverse lines
- [x] `tac`: reverse file (cat backwards)
- [x] `nl`: number lines

### Terminal / TTY
- [x] `stty`: terminal line settings
- [x] `tty`: print current terminal device
- [x] `reset`: reset broken terminal
- [x] `clear`: clear terminal screen
- [x] `script`: record terminal session
- [ ] `tmux`: terminal multiplexer

### Package management
- [ ] `dnf`: Fedora/RHEL package manager
- [ ] `brew`: Homebrew package manager, common on macOS and useful via Linuxbrew
- [ ] `flatpak`: Flatpak package manager

### Concepts
- [ ] shell expansion order
- [x] quoting rules
- [ ] PATH lookuk
- [ ] HTTP request/response model: methods, headers, status codes, bodies, redirects, caching, cookies, and auth basics[]()
- [ ] fast doc lookup: official docs first, then `site:` search by tool/vendor
- [ ] Terraform lookup model: language docs vs provider docs vs registry module docs
- [ ] browser keyword search shortcuts / DevDocs for fast web-doc lookup
- [ ] cgroups vs namespaces vs systemd units
- [ ] file ownership vs permissions vs ACLs
- [ ] process/session/job distinction
- [ ] package ownership: which package installed this file?
- [ ] OIDC and OAuth flow

### Pre-commit
- [ ] `pre-commit`: run the same local hooks as CI

### Data wrangling
- [ ] `jq`: JSON query/transform — essential for API work, terraform state
- [ ] `yq`: YAML equivalent of jq — critical for ansible debugging

### Containers
Fedora-native defaults apply.
- [ ] `podman`: rootless containers — docker-compatible
- [ ] `docker`: still the lingua franca even if you prefer podman
- [ ] `docker compose`: local multi-container stacks
- [ ] `podman compose`: compose-style podman workflow

### Secrets / credentials
- [ ] `secret-tool`: query/store secrets via libsecret
- [ ] `bw`: Bitwarden CLI

### Python and Node.js
- [ ] `python3`: Python interpreter
- [ ] `pip`: Python package installer
- [ ] `pipx`: install Python CLI apps cleanly
- [ ] `venv`: Python virtual environments
- [ ] `node`: JavaScript runtime
- [ ] `npm`: Node package manager

### Just
- [ ] `just`: command runner (you already use this)

### CLI calculators
- [ ] `bc`: arbitrary-precision calculator for shell math, unit conversions, and quick ops arithmetic

### Environment and dotfiles
- [ ] `stow`: symlink farm manager (your dotfiles)
- [ ] `direnv`: per-directory env vars

### AI coding agents
- [ ] `pi`: coding agent CLI for AI-assisted code/file edits and terminal workflows
- [ ] `claude code`: Anthropic's agentic coding CLI

### Archiving/compression
- [ ] `tar`: tape archive (tar czf, tar xzf)
- [x] `gzip`: gzip compression
- [x] `gunzip`: decompress gzip
- [x] `zcat`: cat compressed files
- [x] `unzip`: extract zip archives

### Spell checking / writing
- [ ] `aspell`: interactive CLI spell checker for prose, notes, and Markdown
- [ ] `hunspell`: dictionary-based spell checker used by many editors and language packs
- [ ] `codespell`: catch common misspellings in code, docs, and config files
- [ ] `typos`: fast repo-wide spell checker for source, filenames, and CI

### Search and navigation
- [x] `fzf` is a composable fuzzy finder that transforms how you navigate
- [x] `fd`: fast, intuitive find replacement. Pairs with fzf
- [x] `rg`: ripgrep — fast recursive grep with sane defaults
- [ ] `zoxide`: smarter cd with frecency tracking
- [ ] `delta`: beautiful git diffs, pairs with lazygit

## Completed

### Docs / discovery
- [x] `man`: primary system manuals
- [x] `apropos`: find commands by keyword
- [x] `whatis`: one-line command descriptions
- [x] `whereis`
- [x] `info`: GNU manuals when `man` is thin

### File operations
- [x] `find`: search filesystem
- [x] `locate`: fast filename lookup via a prebuilt database
- [x] `updatedb`: refresh the `locate` database
- [x] `chmod`: change permissions
- [x] `chown`: change ownership
- [x] `chgrp`: change group
- [x] `stat`: file metadata
- [x] `file`: detect file type
- [x] `realpath`: resolve symlinks
- [x] `readlink`: read symlink target
- [x] `gio`: GLib/GVfs file and metadata operations
- [x] `basename`: strip directory from path
- [x] `dirname`: strip filename from path
- [x] `mktemp`: create temp file/dir
- [x] `mkfifo`: create named pipes
- [x] `split`: split a file into smaller chunks
- [x] `truncate`: shrink or extend a file to a specific size
- [x] `install`: copy with permissions
- [x] `link`: create hard link
- [x] `unlink`: remove single file
- [x] `lsattr`: list Linux extended file attributes

### Process management
- [x] `ps`: process list
- [x] `pstree`: process tree view - parent/child relationships at a glance
- [x] `kill`: send signal
- [x] `killall`: kill by name
- [x] `pgrep`: find process by pattern
- [x] `pkill`: kill by pattern
- [x] `top`: process monitor
- [x] `htop`: better process monitor
- [x] `bg`: background job
- [x] `fg`: foreground job
- [x] `jobs`: list shell jobs
- [x] `nohup`: survive logout
- [x] `wait`: wait for background jobs
- [x] `nice`: set priority
- [x] `renice`: change priority
- [x] `timeout`: run with time limit

### Networking / connectivity
- [x] `curl`: HTTP/API checks

### Editors
- [x] `nvim`: your editor
- [x] `vim`: fallback
- [x] `vi`: minimal vim
- [x] `view`: read-only vim
- [x] `ctags`: generate source navigation tags

### Important config locations
- [x] `/etc/profile`, `~/.profile`, `~/.bashrc`, `~/.zshrc`

### Shell scripting quality
- [x] `shellcheck`: static analysis for shell scripts — catches real bugs
- [x] `shfmt`: shell script formatter (use with conform.nvim)
	- Add this to the pre commit.

## Scope

- Current work: GitHub and GitHub Actions, `pre-commit`, `just`, Terraform, AWS, Ansible playbooks, PostgreSQL, Node.js, Python, containers, Fedora (`dnf` and Flatpak), Homebrew, `bw`, `secret-tool`, `stow`, `direnv`, Pi, and Claude Code.
- Universal terminal foundations also stay active: Git, Zsh, shell/Unix fundamentals, editing, `fd`, `rg`, `fzf`, `bc`, and spelling tools.
- Everything else is parked in [[command-triage-lazy]] unless real work selects it.
