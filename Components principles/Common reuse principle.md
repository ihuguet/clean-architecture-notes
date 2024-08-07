> Classes that aren't reused together should not be grouped together

> Don't force to users to depend on things that they don't need

Classes and [[module]]s that tend to be reused together, should be together in a [[component]], but more importantly those that are not closely related shouldn't be put together.

This is the equivalent of the component's [[Interface segregation principle]], but applied to components.

If we make a change in a component, users of the component might need to validate again with the new version, even if they don't use the part that has changed.

Ideally, when we depend on a component we should depend on all its classes, not only on some of them (*note to myself: what about generic libraries like nispor? They usually break this principle but it make sense to do it this way, we are not going to split nispor into 30 subpackages...*).
