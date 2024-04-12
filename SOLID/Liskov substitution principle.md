> Functions that use references to base classes must be able to use objects of derived classes without knowing it.

This can be used for base and derived classes in OOP languages, but also to any other software design that allows, in any way, to use abstractions (as a base class is) and implementations (as a derived class is):
- REST web endpoints
- Duck typed languages that accepts any class and call to a specific method, expecting it to have a specific firm.
- Interface and implementations in Java, Traits and impls in Rust...

Basically, it can be used to any software design that uses, in any way, abstractions implemented by concrete entities. Abstractions can be seen as contracts that must be respected by all implementors.

Good example to understand: the square/rectangle problem. A square seems to be a subclass of a rectangle, but it can't be because if you call `set_width` on it, you also modify the height, thus violating an implicit contract of rectangle. Users would need to use `if/else` to differentiate between square and rectangle before calling its functions, violating LSP.

References:
- https://web.archive.org/web/20150905081111/http://www.objectmentor.com/resources/articles/lsp.pdf