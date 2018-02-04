# Design patterns

## Categories

- Creational patterns
    - Patterns that cover object creation

- Structural patterns
    - Describes relationships between entities

- Behavioral patterns
    - Identifies common communication patterns between objects

## Patterns

- Creational
    - Abstract factory
        - Provides a interface for creating related objects without needing to specify class
        - `new` considered harmful
        - Goal is to abstract object creation depending on business logic (etc)
        - Each "product" has a factory
        - Source [1](https://sourcemaking.com/design_patterns/abstract_factory), [2](https://github.com/faif/python-patterns/blob/master/creational/abstract_factory.py)
    - Builder
    - Factory method
        - Define a interface for creating object, but let subclass decide class
        - `new` considered harmful
        - "Creates objects without having to specify the exact class."
        - "Abstract Factory classes are often implemented with Factory Method"
        - With this method you can implement a object pool or return the same object depending pn arguments
        - Source [1](https://sourcemaking.com/design_patterns/factory_method), [2](https://github.com/faif/python-patterns/blob/master/creational/factory_method.py)
    - Prototype
    - Singleton
        - Ensure a class has only one instance, and provide a global point of access to it.
        - Is created in a lazy manner
        - Source [1](https://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Singleton), [2](https://en.wikipedia.org/wiki/Singleton_pattern), [3](https://sourcemaking.com/design_patterns/singleton)

- Structural
    - Adapter
        - Lets you provide a different interface for a class (that would otherwise be incompatible)
        - Wrap a existing class into a new interface (Adapter reuses a old interface)
        - "Makes things work after they're designed"
        - Example: `Adapter(dog, make_noise=dog.bark)`
        - Source [1](https://github.com/faif/python-patterns/blob/master/structural/adapter.py), [2](https://sourcemaking.com/design_patterns/adapter)
    - Bridge
        - "Makes things work before they are designed"
        - "Decouple an abstraction from its implementation"
        - Source [1](https://sourcemaking.com/design_patterns/bridge), [2](https://github.com/faif/python-patterns/blob/master/structural/bridge.py)
    - Composite
        - Treat a list of objects the same way as a single type of object
        - Source [1](https://github.com/faif/python-patterns/blob/master/structural/composite.py), [2](https://sourcemaking.com/design_patterns/composite)
    - Decorator
        - Dynamically add new features to objects without changing its implementation
        - Source [1](https://github.com/faif/python-patterns/blob/master/structural/decorator.py), [2](https://sourcemaking.com/design_patterns/decorator)
    - Facade
        - Provides a simple unified interface to a more complex system
        - Example: Starting a computer
        - Source [1](https://github.com/faif/python-patterns/blob/master/structural/facade.py), [2](https://sourcemaking.com/design_patterns/facade)
    - Flyweight
    - Proxy

- Behavioral patterns
    - Chain of Responsibility
    - Command
    - Interpreter
    - Iterator
        - Lets you access elements of an aggregate object sequentially without exposing the underlying structure of the object.
        ... or in less words "Traverses a container and accesses the container's elements."
        - Source [1](https://sourcemaking.com/design_patterns/iterator), [2](https://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Iterator), [3](https://github.com/faif/python-patterns/blob/master/behavioral/iterator.py)
    - Mediator
    - Momento
    - Observer (or `Publish/Subscribe` or `Event Listener`)
        - Fefines a one-to-many relationship so that when one object changes state (like bidding, where bidders are observers and auctioneer are subject)
        - or in less words: "Maintains a list of dependents and notifies them of any state changes."
        - Defines a subject and observers
            - Subject: Reponsible for maintaining a list of observers and notifying them
            - Object: Register/unregister to an object and react to change
        - Is a competing pattern with Mediator
        - Source [1](https://sourcemaking.com/design_patterns/observer), [2](https://github.com/faif/python-patterns/blob/master/behavioral/observer.py), [3](https://en.wikipedia.org/wiki/Observer_pattern)
    - State
    - Strategy
        - Enables selecting an algorithm at runtime.
        - "Strategy lets you change the guts of an object. Decorator lets you change the skin."
        - Example: "Modes of transportation to an airport"
		- Strategy is like Template Method except in its granularit
        - Source [1](https://sourcemaking.com/design_patterns/strategy), [2](https://sourcemaking.com/design_patterns/strategy), [3](https://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Strategy), [4](https://github.com/faif/python-patterns/blob/master/behavioral/strategy.py)
    - Template method
        - "Define the skeleton of an algorithm in an operation, deferring some steps to client subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm's structure."
		- Template Method uses inheritance to vary part of an algorithm. Strategy uses delegation to vary the entire algorithm.
        - Source [1](https://sourcemaking.com/design_patterns/template_method), [2](https://en.wikipedia.org/wiki/Template_method_pattern), [3](https://en.wikibooks.org/wiki/Computer_Science_Design_Patterns/Template_method), [4](https://github.com/faif/python-patterns/blob/master/behavioral/template.py)
    - Visitor



- Sources:
    - [Gang of Four Design Patterns](http://www.blackwasp.co.uk/gofpatterns.aspx) - The 23 original patterns
