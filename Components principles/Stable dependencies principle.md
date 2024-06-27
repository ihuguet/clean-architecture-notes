> Depend in the direction of stability.

Sometimes the design of the software needs to change. We say that those components that sees lot of changes are [[volatile]].

On [[component]]s that we want or expect to be [[volatile]], there must not depend lot of other components because each change will be too difficult.

The contrary of [[volatile]] is [[stable]]. Something is stable if it requires lot of work to change it.
- A element on which many others depend on is very [[stable]] because it's difficult to change.
- A element on which none or very few others depends is very [[volatile]] because it's easy to change.

Stable components must not depend on less stable ones. If the less stable ones changes, the change needs to be propagated to the stable one, and to all its dependent components. To solve this we can use the [[Dependency inversion principle]].

> [!info]
> Robert C. Martin calculates the inestability as $I = n_o / (n_i + n_o)$, being $n_i$ the number of classes that depends on the component and $n_o$ the number of classes from the component that depends on external classes.

