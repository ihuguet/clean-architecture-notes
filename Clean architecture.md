What is software architecture?
----------------------
It is the form that we give the the software system, deciding how to divide it in components, how they are organized and how the communicate with each others.

It must support these aspects of the system life cycle:
- [[Development]]
- [[Deployment]]
- [[Use cases and operation]]
- [[Maintenance]]

> [!note]
> The most important benefits of a good architecture are **not** in how the software works. Lot of software with bad architectures works really well. This doesn't mean that we should not care of it, it means that the main benefits apply to development and maintenance because the costs shifts much towards them.

To properly support the system's life cycle, these are the main strategies that a good architecture should support:
- Having a good [[Decoupling]] of the system's components.
- Having a good understanding about what the system's [[Policies]] are, and how the architecture has to be designed around them.
- [[Keeping options open]] as much time as possible.

Different proposals about what a good architecture should look like have been developed. Many of them share various common aspects and similar designs that we can summarize in what we call **clean architecture**.

Clean architecture
----------
Different proposals about what a good architecture should look like have been developed, such as hexagonal architecture (aka ports and adapters architecture, DCI or BCE. Many of them share various common aspects and similar designs that we can summarize in what we call *clean architecture*.

They have some differences in details but all them are similar and have the same goal of separation of concerns, and all them achieve it dividing the software in layers. All them also separate business rules from user and system's interfaces.

All them has at least these characteristics:
- Independent of any framework
- Testable
- Independent of the UI
- Independent of the DDBB
- Independent of any external agency

All these architectures achieve these with slightly different proposals for what we call the **dependency rule**.
Dependency rule
------------
There are at least 4 layers that need to exist in a software architecture. They are often represented as concentric circles, being the highest level the most inner ones. Therefore, we get the dependency rule:

> Code dependencies must only point towards the center of the circle, towards the high level policies.

*Note that this is not a new rule, it was already implied by the [[stable dependencies principle]] and [[Policies#policies and level]]*

TODO: insert image of the clean architecture circles

Elements in internal circles must know nothing about outer circles. They mustn't use any name (variables, functions, classes...) or data structures from them.

The 4 layers are (from inner to outer):
- Entities: the domain rules
- Use cases: the application rules
- Interface adapters: presenters, controllers, bridges...
- Frameworks and drivers: DDBB, web, I/O, devices, external interfaces, UI frameworks...

The *interface adapters* layer is a group of adapters that convert the data between the formats used by entities and use cases layers and the format used by external elements like the database, the web, the GUI framework, etc. For example, this layer will contain the MVC of the GUI or the SQL sentences needed to persist the data. The inner circles must know nothing about them.

The data passed across the boundaries of the different layers normally has to be simple data structures as explained in [[Decoupling#Data that crosses the boundaries]].

However, it must be noted that architectural boundaries are costly, they take a high effort to implement and maintain. In many cases, it is preferable not to abuse of them, or use only [[Partial boundaries]] instead.

> [!note]
> You may decide to have more than 4 layers, but keep always in mind the dependency rule, with the dependencies pointing towards the center.

Additional considerations
-----------
There are some quite singular components that deserve some additional explanations:
- [[The main component]]
- [[Tests]]

There are also some common misconceptions that need to be clarified:
- [[Service oriented architectures]].

Summary
-------
https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html