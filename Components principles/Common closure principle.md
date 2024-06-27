> Classes that change together, belong together

>  Put together those classes that changes at the same times for the same reasons. Don't put together those classes that changes at different moments and for different reasons.

A [[component]] shouldn't have more than one reason to change. This is the equivalent of the [[SOLID]]'s [[Single responsibility principle]], but applied to components.

Putting together those classes that changes for the same reasons makes that, when we have to do a change, the change is done in only one or very few components. We will only need to implement and validate again the component and those that depends on it. If many components changes, many dependencies need to be implemented and validated again.

Note: risk of making too big components, don't abuse, ensure that they actually change for the same reasons.