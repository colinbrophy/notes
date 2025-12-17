
* Emacs is a **shared-mutable-state system** with no ownership or isolation.
* “Composability” relies on hooks and global state, not real boundaries.
* Single-threaded but **reentrant**, so behaviour depends on timing and history.
* Automations and workflows **inevitably rot** and require debugging.
* “Magic” comes from abstraction leaks, not sound design.
* [[Org-mode]] works only because it is slow, constrained, and heavily patched.
* Most of Emacs’ advantages are now obsolete.

However one pro is that you get a uniform text like interface to work with lots of plugins/programs. But [[Neovim]] has this capacity now.

**Conclusion:**
Emacs is architecturally unsound by modern standards. Use it only if you explicitly want to hack the editor itself. For productivity and reliability, it is a poor choice.
