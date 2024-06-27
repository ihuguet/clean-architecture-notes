The greatest advantage of Object Oriented Languages is polymorphism, which allows us to use **dependency inversion**.  You can achieve all them with C, for example, but OO languages allow to use them in an easier and safer way, not depending on manual conventions.

The program control flow forces us to call lower level functions from higher level ones. Normally, this makes that the high level files/modules need to import lower level ones, so a dependency to them is created in the source code.

**Dependency inversion** means to depend on abstractions (i.e. interfaces) that are implemented somewhere else. This way, higher level modules don't depend on the lower level modules that implement those abstractions, but at runtime these lower level modules are actually used.

The abstractions/interfaces belong to the high level component, and they **must be very stable** because changing them might imply having to change all the concrete implementations.

However, it is not realistic to pretend depending only on abstractions. It is OK to have direct dependencies when:
- The dependency is on a very stable module. For example a `String` class, it will change almost never and with great care.
- Small group of interrelated modules/components can have direct dependencies between them, still being separated from the rest of the system.

> [!note]
>   The contrary to *stable* elements are *volatile* elements. We must never depend on volatile elements. These volatile elements can be the implementation of a stable abstraction, though.

**Factories**: the concrete classes that implements the interfaces needs to be instantiated and injected somehow. Normally, factories are used for that, choosing what concrete factory to use from `main`, for example.

Practical example:
- In a logger app we have a class called `LogEvent`. This is a core class that belongs to the [[bussiness rules]], so it is a high level module.
- We need to save it, but where to save it is a detail that belongs to lower layers, `LogEvent` doesn't need to know if it's saved as a line of a txt file or to a database.
- We create the interface `LogEventSaver` with a `save` method. The interface is an abstraction belongs to the same high level component than `LogLevel`. It must be stable because many concrete implementations will implement it.
- We create the concrete classes `DiskSaver` and `DatabaseSaver`, both implementing `LogEventSaver`. Note that they can implement more interfaces, like `UserConfigSaver` in the same concrete classes (but don't be tempted of merging the interfaces into a big one, thus breaking the [[Interface segregation principle]]).

References;
- https://web.archive.org/web/20150905081103/http://www.objectmentor.com/resources/articles/dip.pdf