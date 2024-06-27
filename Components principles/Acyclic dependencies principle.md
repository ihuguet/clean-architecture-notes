> The dependencies between components must not form cycles

Each [[component]] is developed and released individually. The developers of other components that depends on them can choose when and how start using the new version. Integration of all components happens in small incremental steps.

However, if the dependency graph contains a cycle, the components belonging to that cycle cannot be developed independently anymore. Probably they can't be tested independently anymore, either. They effectively become a new big component.

*A cycle is formed when a component depends on another that also depends on the first one, either directly or via one of its direct dependencies.*

To break the cycle there are 2 main possibilities:
- Use the [[Dependency inversion principle]]
- Create a third [[component]] to depend on