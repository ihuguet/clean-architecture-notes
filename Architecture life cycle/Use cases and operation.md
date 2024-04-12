Use cases
----------
The architecture has to support what the system is supposed to do. However, there is no much that the architecture can do in this sense, other than trying to make as obvious as possible what the system does (thus, supporting the maintenance, actually).

In this sense, it is a good symptom the "architecture that screams". The architecture must scream what's the purpose of the system, in the same way that, when you look at the drawings of a building it screams "HOME" or "LIBRARY". Your system must scream things like "INVENTARY SYSTEM", not "RUST PROJECT" or "SPRING APP".

Operation
----------
The architecture must support the requirements regarding how the system must operate.

For example, if the system has to support 100k clients/second, the overall design must support it, maybe with a division in different services that can run in parallel in different servers.

Even if it's not intuitive, this is one of the decisions/options that we should try to keep open as much time as possible. For example, an architecture that maintains a good decoupling between it's components with few assumptions about how they communicate will be easier to change from a monolith to a multi-services design.