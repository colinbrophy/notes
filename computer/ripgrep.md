To search only `.yml` files with ripgrep:

```bash
rg -g '*.yml' 'pattern'
```

Or use the type flag if you want both `.yml` and `.yaml`:

```bash
rg -t yaml 'pattern'
```

A few other handy options:

- `--glob` / `-g` for specific patterns: `rg -g '*.yml' -g '!test/*' 'pattern'` (exclude test dir)
- List files only: `rg -g '*.yml' -l 'pattern'`
- Case insensitive: `rg -ig '*.yml' 'pattern'`