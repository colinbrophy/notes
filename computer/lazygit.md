The core problem you identified was that the Git CLI lacks **live, interactive state visibility** — you were constantly retyping `git status` and `git diff` to poll state rather than just seeing it update in real time.

We decided it was better than [[neogit]] as it was a standalone tool, although had some jank as it's not as well integrated into [[Neovim]]. We can revisit later if a problem.