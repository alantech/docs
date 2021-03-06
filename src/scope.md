#### Implied Structure: Scope

Scoping is a concept common in many programming languages, it is a way to determine what is available for use in your code or not, and can be thought of as a tree of maps you can check for a specified name. Module-less languages like C have a single primary scope defined across the entire project (as all source files are simply concatenated together) while functions and blocks[^1] have their own nested scopes.

Module-based languages tend to have two scopes per module, the private module-level scope and the public export scope. Java allows only a single exported element per file (but multiple files per module, remember) declared `public` while private elements are simply left undeclared. Node.js, Python, etc all have this two scope set for each module.

Alan continues that tradition here for ease of use, and like many of the languages does have a wholly-internal root scope that built-in types, functions, etc are defined in that all scopes eventually inherit from. The [Built-ins](./builtins/built_ins.md) section is documentation of this root scope and what it automatically brings to every module.

<!-- TODO: Add some diagrams of scope as different nested sets via Venn diagrams. -->

[^1]: For those who don't know what blocks are, they are the inner bodies of if statements, while/for loops, etc in C, Java, Javascript, Python, etc, and usually surrounded by curly braces. For those who still don't know and must live in some parallel universe where LISP won, they're like immediately-invoked function expressions (IIFEs), and this is exactly how Alan implements that concept under the hood.
