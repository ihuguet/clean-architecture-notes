> A module must have one, and only one, reason to change.

Or, as explained by Robert C. Martin:

> A [[module]] must be responsible of one, and only one, actor [^1].

> [!warning]
> This is the less understood [[SOLID]] principle, probably because the name not being precise. It doesn't mean that a module has to do a single thing. That is a different but similar principle that affects only to functions (a function must do one and only one thing).

Easier to understand with an example: we have this class with these methods:

```
Employee
 - calculatePay
 - reportHours
 - save
```

However, `calculatePay` is payroll department's responsibility, `reportHours` is people department's and `save` is database administrators', 3 different *actors*.

Also, probably `calculatePay` and `reportHours` will share a common function to calculate the regular work hours. If payroll wants a change in how regular hours is calculated, it will affect to `reportHours`, breaking people team's use cases.

The solution is to depend on 3 new classes `PayCalculator`, `HourReporter` and `EmployeeSaver` with access to the data stored at `Employee`, and each one complies with SRP: they do what the have to do and they don't know to the others. `PayCalculator` and `HourReporter` will make their own hours calculation separately.

References:
- https://web.archive.org/web/20150202200348/http://www.objectmentor.com/resources/articles/srp.pdf

[^1]: The term *actor* in this context means *users* or *stakeholders*.
