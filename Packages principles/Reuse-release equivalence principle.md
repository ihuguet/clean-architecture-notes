> The granule of reuse is the granule of release

The release of a [[package]] must be done through a release process with release version numbers.

With a comprehensible release process and versioning, users can decide whether and when to integrate the new release. They can also validate whether all the [[package]]s works well together or not. They can receive support for older releases.

The final goal is to allow reusability (which is the goal of any package/library).

From an architecture/design point of view, this implies that the classes and [[module]]s belonging to a [[package]] must make sense together as a cohesive group and have a common topic or purpose. Being released together under the same version number and release documentation must make sense, both for the author and for the users.

Saying that it must "make sense" is not very specific. However, users will perceive when it makes not. 

> !note
> (own thoughts)
> What if we don't specially care about reuse due to the characteristics of the [[package]] / component? 
> For example, we might have a GUI [[package]] / component but without a process to release it separately because we don't need to reuse?