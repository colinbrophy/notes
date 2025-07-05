
> "Any sufficiently complicated C or Fortran program contains an ad hoc, informally-specified, bug-ridden, slow implementation of half of Common Lisp."

### Key Ideas

- **Greenspun's Rule** critiques how complex systems written in low-level or statically typed languages end up reinventing dynamic features (like scripting, config DSLs, etc.).
    
- Lisp already includes these features natively: macros, eval, dynamic typing, etc.
    

### Why This Happens

- Static languages (e.g. C, Java) often lack tools for:
    
    - Metaprogramming
        
    - Runtime code generation
        
    - Expressive DSLs
        
- So developers build those features manually, usually poorly.
    

### When Static Typing Becomes a Constraint

- Use cases with dynamic structure:
    
    - User-defined rules or plugins
        
    - Heterogeneous data (JSON, YAML)
        
    - Interpreters, scripting engines
        
- In these cases, static typing slows down iteration or forces unsafe workarounds.
    

### Core Insight

You’re often better off using a language that natively supports the kind of abstraction you need, rather than simulating it awkwardly inside another.

### Related Thought

Robert Morris's corollary: _"...including Common Lisp"_ — a nod to the irony that even Lisp implementations often include a messy C core.

---

Useful heuristic: **If you're building a mini-language, ask why your host language makes that hard.**