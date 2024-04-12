Are the tests part of the system? Yes. They are very detailed and concrete, so they are in the most low level / outter circle of the architecture. The dependency from them must go towards the inner of the circle. Nothing depends on the tests, and the tests depends on the internal components.

They must be designed to avoid the _fragile tests problem_. For example, testing business rules with tests that navigates the GUI is a terrible idea: a small change in the GUI will break thousands of tests. A special API with superpowers can be added to internal components to be used by tests.

Also, avoid structural coupling. The tests should depend as less as possible of the structure of the application. Otherwise, small changes in the application makes that lots of tests has to change too.