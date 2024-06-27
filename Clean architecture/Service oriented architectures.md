Architectures based on (micro-)services has become very popular. Among other things, because of 2 reasons which are actually not true:

- Services are decoupled of each other.
- Services can be developed and deployed independently.

Decoupling
------
It looks like services are highly decoupled because they run in different processes. They don't have access to each other's resources and have very well defined interfaces.

This is actually not true. Actually, the interface defined by a service is no more formal, strict or better defined than the interface defined by a function call.

Services are coupled by the information they share: if a new field is added to a data structure which is shared across services is changed, all the services that use it need to change because they need to know what it means.

To implement new features or changes, we might need to change multiple different services, and some services need to have good knowledge about how other services work. The architectural boundaries don't exist between services, but across them. Actually, each service is not an architectural component, but rather it has to be divided with an internal design of components to accommodate to the overall architecture of the system.

Independent development
-----------
The fallacy about decoupling above shows that services cannot be actually developed independently. Services that are coupled by the data they share of by behavior will need to change in a coordinated manner.

Also, there are plenty of examples of big business systems that operate as monoliths based on [[component]]s that are developed independently. Services are not the only option for systems that scale at their development.

Conclusion
----------
Services might be useful or even necessary for the design of certain systems. However, they are not by themselves significant architectural elements. The architecture of a system is defined depending on the boundaries that are traced and the dependencies that crosses those limits, not by the physical mechanisms used to communicate between elements.

It must be noted that a design based on services adds complexity to the development and maintenance of the system, as explained in [[Partial boundaries]].