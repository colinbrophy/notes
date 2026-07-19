---
tags:
  - ai-written
---

# ZSH plugins

Reference:
- [This Zsh config is perhaps my favorite one yet.](https://www.youtube.com/watch?v=ud7YxC33Z3w) - Dreams of Autonomy

Shortlist from the `awesome-zsh-plugins` triage. Prefer one plugin per job; avoid installing duplicate alias packs or overlapping history/navigation tools.

## Hell Yeah Useful

- [ ] Plugin manager: `antidote`, `zgenom`, `znap`, `sheldon`, `zap`, or `zinit` - pick one if not already using a framework.
- [x] Prompt - already handled by a custom minimal prompt in `~/.zshrc`; none of these prompt plugins are installed.
  - [ ] `powerlevel10k`
  - [ ] `starship`
  - [ ] `pure`
  - [ ] `spaceship`
  - [x] custom prompt in `~/.zshrc`
- [x] `zsh-autosuggestions` - Fish-style suggestions from command history.
- [x] Syntax highlighting - highlight commands before execution.
  - [ ] `fast-syntax-highlighting`
  - [x] `zsh-syntax-highlighting`
- [ ] `zsh-autocomplete` - alternative/complement to classic completion if live completion feels useful rather than noisy.
- [ ] `fzf-tab` - replace plain tab menus with fuzzy selection.
- [x] FZF shell integration - fuzzy file, directory and history keybindings.
  - [x] `fzf --zsh`
  - [ ] `fzf-zsh-plugin`
- [x] Better `Ctrl-R` history search - use `atuin` if history search/sync matters.
  - [ ] `fzf-history-search`
  - [x] `atuin`
- [ ] `zsh-history-substring-search` or `history-search-multi-word` - lighter history search upgrade if not using `atuin`.
- [ ] `histdb` or `per-directory-history` - richer or directory-aware command history.
- [x] Frecency-based directory jumping.
  - [x] `zoxide`
  - [ ] `zsh-z`
  - [ ] `z.lua`
- [x] Interactive/fuzzy `cd` - currently provided by `fzf --zsh`, not one of these plugins.
  - [ ] `interactive-cd`
  - [ ] `enhancd`
  - [ ] `fz`
  - [x] `fzf --zsh` `fzf-cd-widget`
- [ ] `fav`, `fzf-marks`, `wd`, or `pins` - named directory bookmarks.
- [x] `direnv` - per-project environment variables.
- [ ] `zsh-completions` - extra completions for common CLI tools.
- [x] Bash-style completions for selected tools - custom `bashcompinit`, not a generic fallback plugin.
  - [ ] `bash-completions-fallback`
  - [ ] `carapace-bin`
  - [x] manual `bashcompinit` for `terraform` and `aws`
- [ ] `completion-sync` - pick up completions added dynamically to `$fpath` or XDG paths.
- [ ] `complete-lastf` - complete the most recently modified file or directory.
- [ ] Completion generation/fallback for tools without good native ZSH completions.
  - [ ] `cod`
  - [ ] `argc-completions`
  - [ ] `inshellisense`
- [ ] `forgit` or `git-fuzzy` - fuzzy Git workflows.
- [x] Clipboard helper - custom `wl-copy` global alias, not a clipboard plugin.
  - [ ] `clipboard`
  - [ ] `system-clipboard`
  - [x] custom global alias `C='| wl-copy'`
- [ ] `copy-pasta` - terminal-native file copy/paste workflow.
- [ ] `safe-rm` or `careful_rm` - safer deletion; only install if comfortable wrapping `rm`.
- [ ] `safe-paste` or `paste-guard` - reduce pasted-command accidents.
- [ ] `shellfirm` - confirmation guard for risky commands.
- [ ] `history-filter` or `passwordless-history` - keep secrets out of shell history.
- [ ] `purge-history-secrets` - scan and purge leaked secrets from shell history.
- [x] Startup caching/deferral - custom daily init cache in `~/.zshrc`, not one of these plugins.
  - [ ] `zsh-defer`
  - [ ] `evalcache`
  - [ ] `lazyload`
  - [ ] `startcache`
  - [x] custom daily cache for `direnv`, `fzf`, `atuin`, `zoxide`, and `codex`
- [x] Completion startup optimization - custom daily `compinit` cache path, not one of these plugins.
  - [ ] `ez-compinit`
  - [ ] `lazycomplete`
  - [x] custom `.zcompdump` freshness check plus `compinit -C`
- [ ] `startup-timer` or `zsh-bench` - diagnose slow shell startup or interactive latency.
- [ ] `command-execution-timer`, `duration`, or `cmd-time` - show how long commands took.
- [ ] `auto-notify`, `notify`, or `zlong_alert` - notify when long-running commands finish.
- [x] Command status - custom prompt shows non-zero exit codes, not one of these plugins.
  - [ ] `nice-exit-code`
  - [ ] `cmd-status`
  - [x] custom red exit-code prompt in `~/.zshrc`
- [ ] `zman`, `popman`, or `explain-shell` - quicker lookup for manuals or command explanations.
- [ ] `command-not-found` - package suggestions for missing commands.
- [ ] `no-ps2` - make incomplete commands insert newlines instead of dropping into an awkward secondary prompt.
- [ ] `edit-select` or `shift-select` - richer command-line text selection/editing.
- [ ] ZLE movement/editing helpers for long command lines.
  - [ ] `zledit`
  - [ ] `zsh-easy-motion`
- [ ] `zsh-vi-mode` - only if using vi-style command editing.
- [ ] `zsh-vi-man` - only if using vi-mode and wanting `Shift-K`-style man page lookup.
- [ ] `zsh-hints` - show ZSH glob/parameter flags and other non-completable hints while learning the engine.
- [ ] `zsh-abbr` or `zsh-abbrev-alias` - fish-style abbreviations if aliases feel too hidden.
- [ ] `expand-space`, `zsh-expand`, or `print-alias` - expand aliases/commands visibly before execution.
- [ ] Fuzzy insertion/search helpers.
  - [ ] `smart-insert`
  - [ ] `fzf-utils`
  - [ ] `fzf-tools`
- [x] SSH host completion/info - host completion is already partly handled by custom `~/.ssh/config` completion.
  - [ ] `ssh-config-suggestions`
  - [ ] `sshinfo`
  - [x] custom SSH host completion in `~/.zshrc`
- [ ] `senv` - show sensitive environment-variable presence in the prompt.

## Maybe / Tiny Config First

Try a small alias, function, option, hook, or environment-variable tweak before installing these as plugins.

- [ ] `mkcd` or `take` - often just `mkdir -p -- "$1" && cd -- "$1"`.
- [ ] `up`, `dot-up`, or `manydots-magic` - parent-directory shortcuts.
- [ ] `bd` - jump to a parent directory by name.
- [ ] `extract` - archive unpacking helper.
- [ ] `sudo` or `sudo-previous-current` - prefix current/previous command with `sudo`.
- [ ] `cd-gitroot` or `cd-reporoot` - jump to repository root.
- [ ] `auto-ls` or `smart-cd` - show context after `cd`.
- [ ] `last-working-directory` - start new shells in the last directory used.
- [ ] `alias-tips`, `you-should-use`, or `alias-finder` - alias reminders.
- [ ] `colored-man-pages` - usually just `LESS_TERMCAP_*` environment variables.
- [ ] `delete-prompt` or `undollar` - clean copied shell prompts from pasted commands.
- [ ] Quote/bracket autopairing.
  - [ ] `zsh-autopair`
  - [ ] `zsh-smartinput`

## Useful If You Use That Tool

- [ ] Version managers: `mise`, `asdf`, `fnm`, `nvm`, `pyenv`, `rbenv`, `jenv`, `sdkman`, `volta`.
- [ ] Git workflows: `git-worktree`, `git-profile`, `git-open-pr`, `git-clean-branch`, `git-to-jj`, `git-lfs`, `git-secret`.
- [ ] Makefiles: `zsh-make-completion`.
- [ ] Containers: `docker-*`, `docker-compose`, `podman` helpers, `dce`, `scad`.
- [ ] Kubernetes: `kubectl`, `kubectx`, `kube-ps1`, `k9s`, `safe-kubectl`, `helm`, `kustomize`, `talosctl`.
- [x] Cloud tools - only AWS is configured.
  - [x] `aws` completion via `/usr/bin/aws_completer`
  - [ ] `gcloud*`
  - [ ] `azure*`
  - [ ] `saml2aws`
  - [ ] `tfaws`
  - [ ] `doppler`
  - [ ] `op`
- [x] Infrastructure as code - only Terraform is configured.
  - [x] `terraform` completion via `bashcompinit`
  - [ ] `terragrunt`
  - [ ] `tfenv`
  - [ ] `tfswitch`
  - [ ] `tgenv`
  - [ ] `tofu`
  - [ ] `packer`
- [ ] Node/JS: `npm`, `pnpm`, `yarn`, `node-path`, `nvm-auto-use`, `run-scripts`, `npms`.
- [ ] Python: `poetry`, `pipenv`, `uv-env`, `venv`, `auto-venv`, `pyenv-lazy`, `pipx`.
- [ ] Ruby/PHP/Java/etc.: `rbenv`, `laravel`, `artisan`, `symfony`, `java-zsh-plugin`, `jabba`, `sdkman`.
- [x] Editors/terminals - only tmux has shell integration.
  - [ ] `vscode`
  - [ ] `vim-plugin`
  - [ ] `nvim-appname`
  - [ ] `iterm2`
  - [ ] `kitty`
  - [x] custom `tmux` title refresh hook
- [ ] Passwords/secrets: `1password`, `bitwarden`, `pass`, `sops-crypt`, `env-secrets`.
- [ ] OS-specific helpers: `macos`, `wsl`, `termux`, `archlinux`, `gentoo`, `systemd`, `apt`, `zypper`.
- [ ] Command snippets/cheatsheets: `navi`.
- [x] CLI completions: install completion plugins only for CLIs already in use.
  - [x] `aws`
  - [x] `terraform`
  - [x] `codex`
  - [x] `opencode`
