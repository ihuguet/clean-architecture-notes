> Stable packages should be abstract packages

High level policies should be stable, so we put them on stable [[package]]s.

To allow stability but still accepting changes, [[stable]] packages need to be designed using the [[Open-closed principle]], enabling to extend them without changing them. We use abstract classes for this.

> [!info]
> Robert C. Martin calculates the level of abstraction as: A = n_classes / n_abstract_classes

Ideally, stable packages has no instability (I = 0) and high abstraction (A = 0). Unstable packages have high instability (I = 1) and low abstraction (A = 0). However, normally we get something in the middle, with some degree of instability and some degree of abstraction. There are 2 zones to avoid:
- Zone of pain (A ~= 0, I ~= 0): very stable but not abstract, so very difficult to change.
  Note that there are elements that can be here without being a problem if they don't change, like the `String` class.
  - Zone of uselessness (A ~= 1, I ~= 1): very abstract but nobody depends on it. Useless.

TODO: add image of the I/A graph