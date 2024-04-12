> Software entities should be open for extension, but closed for modification.

That means that software entities must be extensible without requiring to modify it.

At module level
--------
TBD

At the architecture level
--------
OCP is well understood at the class and [[module]] levels, but it's even more meaningful at the [[architecture level]].

How to achieve adding new features (extending the software) but minimizing the amount of code to change? Correctly separating the pieces that changes for different reasons ([[Single responsibility principle]]) and organizing the dependencies between them with [[Dependency inversion principle]].

We divide the process in classes, and group them in separate components. Dependencies between components must be in a single direction: from lower level components to higher level ones, likely depending on abstractions/interfaces from the high level component (again: [[Dependency inversion principle]]).

> [!remark]
> To protect a component HIGH from changes of component LOW, LOW must depend on HIGH, and not the contrary.
> There is a dependency when the source file of an entity mentions parts of the other entity (in many languages this means to `import`, `use`, `include`, etc. that entity).

### Hidding information
Lower level components can have knowledge of how higher level components work. However, too much knowledge can also harms because it will make more difficult to change the high level component. Exposing abstractions/interfaces or public APIs to interact with high level components mitigate this.

Anyway, keep in mind that high level components are supposed to be more stable and change less, because many other components depends on them.

References:
- https://web.archive.org/web/20150905081105/http://www.objectmentor.com/resources/articles/ocp.pdf