- **Metadata**
- [[Code]]
- [[Blogging]]
- Summary: Design patterns are reusable concepts to solve common problems in software design.


- **Creational**
- [Creational patterns](https://en.wikipedia.org/wiki/Creational_pattern)  are ones that create objects, rather than having to instantiate objects directly. This gives the program more flexibility in deciding which objects need to be created for a given case.
    - [Abstract factory](https://en.wikipedia.org/wiki/Abstract_factory_pattern)  groups object factories that have a common theme.
    - [Builder](https://en.wikipedia.org/wiki/Builder_pattern)  constructs complex objects by separating construction and representation.
    - [Factory method](https://en.wikipedia.org/wiki/Factory_method_pattern)  creates objects without specifying the exact class to create.
    - [Prototype](https://en.wikipedia.org/wiki/Prototype_pattern)  creates objects by cloning an existing object.
    - [Singleton](https://en.wikipedia.org/wiki/Singleton_pattern)  restricts object creation for a class to only one instance.



- **Structural**
- These concern class and object composition. They use inheritance to compose interfaces and define ways to compose objects to obtain new functionality.
    - [Adapter](https://en.wikipedia.org/wiki/Adapter_pattern)  allows classes with incompatible interfaces to work together by wrapping its own interface around that of an already existing class.
    - [Bridge](https://en.wikipedia.org/wiki/Bridge_pattern)  decouples an abstraction from its implementation so that the two can vary independently.
    - [Composite](https://en.wikipedia.org/wiki/Composite_pattern)  composes zero-or-more similar objects so that they can be manipulated as one object.
    - [Decorator](https://en.wikipedia.org/wiki/Decorator_pattern)  dynamically adds/overrides behaviour in an existing method of an object.
    - [Facade](https://en.wikipedia.org/wiki/Facade_pattern)  provides a simplified interface to a large body of code.
    - [Flyweight](https://en.wikipedia.org/wiki/Flyweight_pattern)  reduces the cost of creating and manipulating a large number of similar objects.
    - [Proxy](https://en.wikipedia.org/wiki/Proxy_pattern)  provides a placeholder for another object to control access, reduce cost, and reduce complexity.


- **Behavioural**
- Most of these design patterns are specifically concerned with communication between objects.
    - [Chain of responsibility](https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern)  delegates commands to a chain of processing objects.
    - [Command](https://en.wikipedia.org/wiki/Command_pattern)  creates objects which encapsulate actions and parameters.
    - [Interpreter](https://en.wikipedia.org/wiki/Interpreter_pattern)  implements a specialised language. - [[Interpreter Pattern]]
    - [Iterator](https://en.wikipedia.org/wiki/Iterator_pattern)  accesses the elements of an object sequentially without exposing its underlying representation.
    - [Mediator](https://en.wikipedia.org/wiki/Mediator_pattern)  allows  [loose coupling](https://en.wikipedia.org/wiki/Loose_coupling)  between classes by being the only class that has detailed knowledge of their methods.
    - [Memento](https://en.wikipedia.org/wiki/Memento_pattern)  provides the ability to restore an object to its previous state (undo).
    - [Observer](https://en.wikipedia.org/wiki/Observer_pattern)  is a publish/subscribe pattern which allows a number of observer objects to see an event.
    - [State](https://en.wikipedia.org/wiki/State_pattern)  allows an object to alter its behaviour when its internal state changes.
    - [Strategy](https://en.wikipedia.org/wiki/Strategy_pattern)  allows one of a family of algorithms to be selected on-the-fly at runtime.
    - [Template method](https://en.wikipedia.org/wiki/Template_method_pattern)  defines the skeleton of an algorithm as an abstract class, allowing its subclasses to provide concrete behaviour.
    - [Visitor](https://en.wikipedia.org/wiki/Visitor_pattern)  separates an algorithm from an object structure by moving the hierarchy of methods into one object. - [[Visitor Pattern]]
