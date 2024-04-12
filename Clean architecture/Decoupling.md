Decoupling by layer
----------
We can use the [[Single responsibility principle]] and the [[Common closure principle]] to separate things that change for different reasons.

For example, inside a single use case:
- The UI.
- **[[Domain rules]]**: general business rules not specific to our application. For example, how to calculate the interest of a bank account.
- **[[Application rules]]**: business rules more tied to our specific application. For example, a form validation.
- The data base.

All these elements changes at different times for different reasons. They belong to different horizontal layers that has to be decoupled from each other, even if all them are supporting to the same use case.

Decoupling by use case
----------

Use cases also change for different reasons than the others. Dividing the horizontal layers by use cases, like dividing in small vertical slices of the layer, is very natural and helps to add or change other use cases without affecting the existing ones.

Decoupling modes
----------
1. At source level: control the dependency between modules to make that changes in one module doesn't affect much to others.
   All the components share the addresses space and communicate through function calls. (*note: were not components separate packages?*)
2. At deployment level: control the dependency between installable units. They can be linked statically or dynamically.
   As in the source level decoupling, components lives in the same process, sharing addresses space and communicating through function calls.
3. At process level: different local processes, thus running in different address spaces, but on the same machine communicating via IPC protocols, sockets, shared memory, etc.
4. At service level: different independent services through network packets only.

It is difficult to know which one to use at the beginning, and it even can change when the product evolves. The solution is to design it in a way that the decoupling of the components allow to change from a monolith to a services model if needed. This change doesn't need to be exactly a trivial change, but the architecture has to facilitate it.

*Note: some people choose to go to (micro-)services by default. This is expensive in terms of development efforts, system resources and costs, and often it probes to be not necessary.*

Tracing boundaries
----------
We should draw lines acting as boundaries between things that matters and things that doesn't, and those boundaries must only be crossed in one direction: towards the core business rules.

For example, the business rules doesn't care about what database we choose and how it works, because the business rules are the same with one or another. We put a limit between them, and the DDBB depends on the business rules, and not the contrary: the business rules only knows that there is a bunch of functions that they can call to save the data (the interface), and we call them indirectly thanks to the [[Dependency inversion principle]].

However, it must be noted that these boundaries are costly to implement and to maintain. In some cases it is preferable not to abuse of them, or use only [[Partial boundaries]].

Plugin architecture
----------
The boundaries that we trace and the rule about how to cross them ends up creating kind of a pattern in the addition of components that is quite familiar to anyone: it's the same pattern used to support third-party plugins.

This way, we start treating any lower level component as a plugin of the higher level component. This way we allow to use many different plugins with the same interface.  For example, allowing to use different UIs (web, GUI, console...) or databases.

The replacement won't always be trivial, and sometimes we'll need to do changes in the interface that we designed because we didn't anticipate some of the new requirements, but certainly this plugin based design will help.

Data that crosses the boundaries
----------
The data that cross the boundaries normally has to be simple data structures.

They can be actual data structures, data transfer objects (DTO), function arguments, hashmaps, etc.

These data structures should only have variables with public data **without any implied behaviour or logic**.

False duplication
---------
TODO: chapter 16