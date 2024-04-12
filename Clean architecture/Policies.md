Software systems are, in essence, a set of declarations of policies. If the policies are complex they can be divided in smaller subsets of policies. 

*Example: some policies describe how to calculate certain business rules, others describes how to format some reports, others how to validate input data.*

Separating and grouping these policies and defining the dependencies between them properly is one of the main goals of a good architecture.
Policies and details
-------------
Elements of a software system belong to two main categories:
- **Policies**: business rules and use case, here is where the highest value is.
- **Details**: required elements to allow humans and other systems to interact with the policies, but without affecting how they work. Are details: IO devices, DDBBs, frameworks, etc.

Good architecture recognizes the policies as its fundamental element, and making the details irrelevant for the policies.

For example, you don't need to choose a DDBB since the beginning because the policies should not depend on the DDBB we choose. You don't need to choose a web server or the create a REST API since the beginning, the policies should work with others too.

Policies and level
------------
A strict definition of "level" is the distance to the inputs and outputs. The farther a policy is from the inputs and outputs, the higher is its level.

> [!important]
> The direction of dependencies must go always from low level components to high level ones.

Business rules
-----------
Business rules are those rules that also exists even if they are not automated by the program. They are *critical business rules*, and usually they require some information to work that we'll call *critical business data*.

For example, a banking loan is something that can exist outside of the program and used manually. It requires some *critical business data* such as the interest rate, the loan balance, the payments plan, etc.

Use cases
---------
They can only exist inside the software system. They define how the automated system is used and how it, at a time, invokes and uses the *critical business rules*.

*Use cases* has a lower level than the *critical business rules*. This means that they know and depend on the *critical business rules*, but the *critical business rules* don't even know that the *use cases* exist.

In the same way, it is important to note that the *use cases* are still *policies*, so they must not depend on any *detail* such as how the UI presents the data, how the data is obtained from the user, etc. because those are lower level components. They must never use data structures such as `HttpRequest`. They must communicate with lower level layers through simple data structures both to request and send input and output data.