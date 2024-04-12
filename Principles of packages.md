Cohesion of packages/components
-------------------
There are some principles to apply to the design of [[package]]s, which are quite equivalent to the [[SOLID]] principles that applies to [[module]]s.

- [[Reuse-release equivalence principle]] (REP)
- [[Common closure principle]] (CCP)
- [[Common reuse principle]] (CRP)

These principles are in tension:
- REP and CCP are inclusive, they tend to make packages bigger. CRP is excluyent, it tends to make packages smaller.
- If you only focus on REP and CRP, many packages will be affected when doing simple changes. If you only focus on REP and CCP, you'll generate too many unnecessary releases.

The team needs to find the equilibrium point depending on the characteristics of the project. Normally this point also moves when the development matures: at first it is more important to facilitate the maintenaince and development (CCP) even if it harms the ease of reuse (REP), but when the project has lots of users you need to shift towards ease of reuse (REP).

TODO: add image of the graph showing the tension

Coupling of packages/components
--------------------
- [[Acyclic dependencies principle]] (ADP)
- [[Stable dependencies principle]] (SDP)
- [[Stable abstractions principle]] (SAP)

SDP and SAP combined are the equivalent to [[Dependency inversion principle]] but for [[package]]s.
Up to down design is not possible
------------------
All the information from above shows something: the design of the [[package]]s structure cannot be done from top to down, it's something that evolves when the system grows and change.

This is because the structure doesn't reflect the application functionality, it's a map about the capacity to generate and maintain the application.

When we begin to develop an application, we don't know much about the actual design of the classes that will be used, so we don't know how to group them nor how to apply the principles from above.