To see the history of a specific line using `git blame`, you can use:

```bash
git blame -L <start>,<end> <file>
```

For example, `git blame -L 42,42 main.py` shows who last modified line 42.

To see the **full history** of a line (not just the last change), use `git log` with `-L`:

```bash
git log -L <start>,<end>:<file>
```

This traces the evolution of those lines through commits, showing diffs at each step. For a single line: `git log -L 42,42:main.py`

You can also trace a function's history with `git log -L :<funcname>:<file>`.

To stash only unstaged changes (keeping staged changes intact):

```bash
git stash -k
```

This stashes everything except what's in the index, so your staged changes remain staged and ready to commit.
