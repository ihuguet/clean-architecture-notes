The humble object pattern was designed to help with the testability of elements with difficult to test behaviors. We separate this behavior into 2 different modules:
- A humble object: it contains all the difficult to test parts, reduced to the minimum expression.
- Other module that contains the parts of the behavior that we can test and have been extracted from the humble object.

For example, a GUI is difficult to test, so we divide it into:
- A `Presenter` that contains the behaviors that we can test. For example, it receives a date in a `Date` class, convert it to a properly formatted `String` and put that value into a `ViewModel`.
  The `ViewModel` can also contain, for example, boolean values with modifiers on how to display the values, for example to display the date in red color. These modifiers are also set by the `Presenter`.
- A `View` object, which is the *humble object*, that just takes the values from the `ViewModel` and pass them to the GUI, probably using a GUI framework.

We cannot easily test the `View`, but we can easily test the `Presenter` by checking the final value that it has created in the `ViewModel`.

Database gateways are another example of *humble objects*. They are called from the *use cases* (via an abstraction because they have lower level) and they convert the high level operation such as `getUserInfo` required by the business rules into an SQL sentence. They can be easily mocked to allow unit testing on the higher level entities.