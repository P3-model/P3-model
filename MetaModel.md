# P3 Meta Model *[draft]*

P3 Meta Model is a set of basic abstractions used to structure our knowledge about the system.

Key terms in IT have often many meanings so we strongly encourage you to read this section to get to know how these terms are used in P3.

P3 Model is designed with extensibility in mind so that it could satisfy specific needs of any system.

## System

TODO

## Perspective

Perspectives is a viewpoint from which we look as the system. Each perspective gathers different kind of Elements from which the system is built.

We distinguish three main perspectives: **Domain**, **Technology** and **People**. These three perspectives are fundamental and are important for every system.

From **domain perspective** we see a model that reflects business reality and satisfy all functional requirements (e.g. rules, behaviors, terms, use cases, etc.). Model in that sense is not technical solution jet and abstracts from implementation details.

From **technology perspective** we see technical solutions used to implement domain model and satisfy quality attributed (e.g. required latencies, throughput, availability, etc.) and organizational constraints (e.g. owned infrastructure, possessed competences, low requirements, etc.).

From **people perspective** we see for whom and by who the system is developed.

Each of these three perspectives can also have sub-perspectives and the list of sub-perspectives can be extended if needed.

## Element

**Element is independent thing that represents something from our design, implementation, development process or even usage of the system** e.g. use case, DDD aggregate, class or interface, database, end user, stakeholder, development team, etc.

Each perspective contains multiple Elements of different types that represents different aspects of the system. All these Elements of different types are important and it's not a good idea to reduce the number of Element types in the name of simplicity. It's essential complexity that can not be avoided. Instead we need a good structure that put in order all these Elements.

**P3 Model contains basic set of Elements and sub-perspectives that group them to standardize our modeling concepts** and provide common language for system designers. This set of Elements is of course not closed or finite so you can extend it according to your needs. We are also not reinventing the wheel but only providing some high level structure in which we can fit existing and future patterns.

**We intentionally avoid using popular terms like module, container or component** because they have many different meanings in IT world and their meanings from common language don't tell us what it could be in the system.

Full list of Elements grouped by perspectives you can find [here](Elements.md).

## Relation

**Relation is a connection between two Elements which represents some dependencies and cannot exists without these Elements** e.g. Relation *contains* between a Layer and a Class or Relation *is deployed in* between domain model boundary (e.g. DDD Bouneded Context) and deployable unit (e.g. .net application).

**All Relations are symmetric** so if A is in Relation with B then B is also in Relation with A. Names of Relation can be different depending on the direction e.g. domain model boundary *is deployed in* deployable unit but deployable unit contains domain model boundary.

Two Element can have multiple Relations of the same type e.g. Relation *is integrated with* between deployable units because each Relation can have different properties and traits.

## Properties and Traits

**Properties are data that are necessary for given Element or Relation** e.g. name of a class, communication type (sync / async) of *is integrated with* Relation.

**Traits are data that are <u>not</u> necessary for given Element or Relation** but can by attached to it e.g. if given class is a public contract, if it's a command in CQRS meaning, what integration pattern is used in *is integrated with* Relation.

Traits are extensibility points in P3 Model because thanks to them new data (for example related to some new architecture pattern) can be attached to existing Elements.

## Pattern

**Pattern is a constraint imposed on Elements and their Relations, properties and traits** e.g. Clean Architecture restrict possible dependencies between Elements belonging to different Layers.

Pattern can be attached to Element or Relation e.g. Clean Architecture to deployable unit.

It's not mandatory to use Patterns in P3 Model you can use only Elements and Relations. However we strongly recommend to use them because they add a lot of additional meaning to the system and can also be used to automate architecture tests.

## Rationale

Rationale is a justification why we took a given decision.

Rationale can be connected with Element, Relation or Pattern.

Each rationale should contain:

- context
- decision
- alternatives

## View

View is a visualization of Elements and their Relations. View can contain Elements from different Perspectives and Categories.

In P3 Model there are no fixed set of Views

brak sztywnego zestawu; lista najpopularniejszych; nie są związane z konkretnym wzorcem, ale mogą ilustrować wzorce; widok to nie perspektywa, bo możemy łączyć informacje z różnych perspektyw na jednym widoku



