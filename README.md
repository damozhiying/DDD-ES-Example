![Travis](https://travis-ci.org/dsantarelli/DDD-ES-Example.svg?branch=master)
# Domain Driven Design/Event Sourcing Example
Just another [Domain Driven Design](https://en.wikipedia.org/wiki/Domain-driven_design) and [EventSourcing](https://martinfowler.com/eaaDev/EventSourcing.html) example written in Java.
## Some highlights
* The [AggregateRoot](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-core/src/main/java/dddes/core/AggregateRoot.java) abstract class provides a mechanism to guarantee the consistency of changes being made internally by forbidding external objects from holding references to its members.
* The [AggregateRootEvent](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-core/src/main/java/dddes/core/AggregateRootEvent.java) and the
[EntityEvent](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-core/src/main/java/dddes/core/EntityEvent.java) abstract classes are used to represent respectively a change applied to an AggregateRoot and to an Entity.
* [Repositories](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-core/src/main/java/dddes/core/IRepository.java) expose methods for retrieving and saving AggregateRoots by accessing to an [EventStore](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-core/src/main/java/dddes/core/IEventStore.java). You can find simple in-memory implementations [here](https://github.com/dsantarelli/DDD-ES-Example/tree/master/ddd-es/ddd-es-example/src/main/java/dddes/example/infrastructure).
* In this example, [Product](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-example/src/main/java/dddes/example/domain/product/Product.java) and a [BacklogItem](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-example/src/main/java/dddes/example/domain/backlogitem/BacklogItem.java) are two AggregateRoots. [ProductBacklogItem](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-example/src/main/java/dddes/example/domain/product/ProductBacklogItem.java) is an Entity. [StoryPoints](https://github.com/dsantarelli/DDD-ES-Example/blob/master/ddd-es/ddd-es-example/src/main/java/dddes/example/domain/backlogitem/StoryPoints.java) is a ValueObject. These implementations are based on "Implementing Domain Driven Design" book written by Vaughn Vernon.
You will find some [unit tests](https://github.com/dsantarelli/DDD-ES-Example/tree/master/ddd-es/ddd-es-example/src/test/java/dddes/example/domain) showing their behaviors and interactions.