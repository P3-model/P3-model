# P3 Meta Model *[draft]*

P3 Meta Model is a set of basic abstractions used to structure our knowledge about the System.

Key terms in IT have often many meanings so we strongly encourage you to read this section to get to know how these terms are used in P3.

P3 Model is designed with extensibility in mind so that it could satisfy specific needs of any System.

## System

The meaning on the System in P3 Model is broad. **System is not only technical solution but it contains also domain and people aspects.** System is a really complex thing where these additional aspects are as important as technical ones. Whenever we refer to the System we use this broad meaning.

## Perspective

**Perspectives is a viewpoint from which we look as the System.** Each perspective gathers different kind of Elements from which the System is built.

We distinguish three main perspectives: **Domain**, **Technology** and **People**. These three perspectives are fundamental and are important for every System.

From **domain perspective** we see a model that reflects business reality and satisfy all functional requirements (e.g. rules, behaviors, terms, use cases, etc.). Model in that sense is not technical solution jet and abstracts from implementation details.

From **technology perspective** we see technical solutions used to implement domain model and satisfy quality attributed (e.g. required latencies, throughput, availability, etc.) and organizational constraints (e.g. owned infrastructure, possessed competences, low requirements, etc.).

From **people perspective** we see for whom and by who the System is developed.

Each of these three perspectives can also have Sub-perspectives and the list of sub-perspectives can be extended if needed.

## Element

**Element is independent thing that represents something from our design, implementation, development process or even usage of the System** e.g. use case, DDD aggregate, class or interface, database, end user, stakeholder, development team, etc.

Each perspective contains multiple Elements of different types that represents different aspects of the System. All these Elements of different types are important and it's not a good idea to reduce the number of Element types in the name of simplicity. It's essential complexity that can not be avoided. Instead we need a good structure that put in order all these Elements.

**P3 Model contains basic set of Elements and Sub-perspectives that group them to standardize our modeling concepts** and provide common language for System designers. This set of Elements is of course not closed or finite so you can extend it according to your needs. We are also not reinventing the wheel but only providing some high level structure in which we can fit existing and future patterns.

**We intentionally avoid using popular terms like module, container or component** because they have many different meanings in IT world and their meanings from common language don't tell us what it could be in the System.

Full list of Elements grouped by Perspectives you can find [here](Elements/Elements.md).

## Relation

**Relation is a connection between two Elements which represents some dependencies and cannot exists without these Elements** e.g. Relation *contains* between a *layer* and a *class* or Relation *is deployed in* between *code module* and *deployable unit*.

**All Relations are symmetric** so if A is in relation with B then B is also in relation with A. Names of Relation can be different depending on the direction e.g. *code module* *<u>is deployed in</u>* *deployable unit* but *deployable unit* *<u>contains</u>* *code module*.

Two Element can have multiple Relations of the same type e.g. Relation *is integrated with* between *deployable units* because each Relation can have different Properties and Traits.

## Properties and Traits

**Properties are data that are necessary for given Element or Relation** e.g. name of a *class*, communication type (sync / async) of *is integrated with* Relation.

**Traits are data that are <u>not</u> necessary for given Element or Relation** but can by attached to it e.g. if a given *class* is a *public contract*, if it's a *command* in CQRS meaning or if *is integrated with* Relation is in a *hot path*.

Traits are extensibility points in P3 Model because thanks to them new data (for example related to some new architecture pattern) can be attached to existing Elements.

## Pattern

**Pattern is a constraint imposed on Elements and their Relations, Properties and Traits** e.g. *clean architecture* restrict possible dependencies between Elements belonging to different *layers*.

Pattern can be attached to Element or Relation e.g. *clean architecture* to *code module* or whole *deployable unit*.

It's not mandatory to use Patterns in P3 Model. You can use only Elements and Relations. However we strongly recommend to use them because they add a lot of additional meaning (especially useful for developers) to the System and can also be used to automate architecture tests.

## Rationale

**Rationale is a justification why we took a given decision.** In our opinion it's equal important to know current system design and the way how we got there. With that knowledge we can better understand current design, speed up onboarding, facilitate process of changing current design, etc.

Each Rationale should contain:

- **context** - what was the situation in which we took the decision e.g. problems to solve, current design, architecture drivers, etc.
- **decision** - what we chose and why
- **alternatives** - what other solutions we took into consideration and why we didn't choose them

Rationale can be connected with Element, Relation or Pattern.

## View

**View is a visualization of Elements and their Relations.** **It's not a part of a design but only a ad hoc projection** which is needed for a given user in a given situation. P3 Model doesn't contain fixed set of views because in our opinion it's not possible to predict all useful visualization for all Systems. Instead Views in P3 Model are constructed form Elements and Relations depending on current needs.

**View can contain Elements from different Perspectives** e.g. *model boundaries*, *code modules* that *implement* that model, *deployable units* in which *code modules* are *deployed* and *teams* that *maintain* it all. Perspective is like aspect of the System and thus is something objective, View is subjective grouping of selected data of the System.

**View is not primarily a visualization of any Pattern.** We can have Views than contains date not relevant to any Pattern used in the System. We don't need to use patterns at all. Some Views can however contains only element relevant to some Pattern and be used for verification if all constraints of that Pattern are met.



