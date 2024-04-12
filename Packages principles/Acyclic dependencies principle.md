> The dependencies between packages must not form cycles

Each [[package]] is developed and released individually. The developers of other [[package]]s that depends on them can choose when and how start using the new version. Integration of all [[package]]s happens in small incremental steps.

However, if the dependency graph contains a cycle, the [[package]]s belonging to that cycle cannot be developed independently anymore. Probably they can't be tested independently anymore, either. They effectively become a new big [[package]].

*A cycle is formed when a package depends on another that also depends on the first one, either directly or via one of its direct dependencies.*

To break the cycle there are 2 main possibilities:
- Use the [[Dependency inversion principle]]
- Create a third [[package]] to depend on