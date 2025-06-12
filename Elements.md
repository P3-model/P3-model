# P3 Model

The P3 Model is designed to help you define and document the key abstractions in your system. By focusing on the most important concepts and their relationships, it helps avoid the noise and complexity that comes from documenting every detail. This selective approach ensures that your documentation remains clear, maintainable, and truly valuable for understanding the system's architecture.

This document describes all P3 Model *Elements* and *Relations*.

Elements are grouped into three perspectives:

* *Domain* – business concepts implemented in the system
* *Technology* – technical solutions used to run the system
* *People* – people who develop, maintain, and use the system

![Elements.png](Elements.png)

## Table of Contents

### Domain
* [Domain Module](#domain-module)
* [Domain Object](#domain-object)
* [Domain Behavior](#domain-behavior)
* [Business Process](#business-process)

### Technology
* [Deployment Container](#deployment-container)
* [Deployable Unit](#deployable-unit)
* [API](#api)

### People
* [Development Team](#development-team)
* [Business Organizational Unit](#business-organizational-unit)
* [Actor](#actor)

### Supporting Concepts
* [Tagging System](#tagging-system)

---

## Domain

### Domain Module

Domain Modules are the **primary way** to organize and structure your system's domain model. They reflect the fundamental need in software development to break down complex systems into *manageable, cohesive units*. The P3 Model recognizes that real-world systems often exhibit multiple levels of modularity, and it allows you to capture this complexity accurately.

For example, in a *modular monolith*, you might have:
* **High-level modules** representing major business capabilities or bounded contexts
* Nested modules within these high-level modules, representing more specific business areas
* Deep hierarchies of modules reflecting the system's internal organization

At the same time, in a *microservices architecture*, the modularity might be much simpler:
* Each microservice might be a single module
* These modules are deployed independently as separate deployment units
* The internal structure of each microservice might be represented as nested modules

In very large systems, modules can also represent **higher-level groupings** that span across multiple bounded contexts or microservices. This allows you to capture organizational structures, business domains, or strategic initiatives that operate at a higher level of abstraction than individual bounded contexts or services.

The P3 Model allows you to capture all these different levels of modularity simultaneously, providing a clear picture of how your system is actually organized in the minds of its architects and developers. This is crucial for maintaining a **shared understanding** of the system's structure and for effective communication between team members.

At its core, each Domain Module groups related domain concepts into *cohesive logical units*. These units can contain:
* **Domain Objects** that represent the data and rules of your business domain
* **Domain Behaviors** that implement the operations and processes
* Other Domain Modules, allowing for nested organization and hierarchical structure

This composition of elements within modules helps maintain clear boundaries and responsibilities, while the ability to nest modules provides the flexibility needed to model complex systems. Each module should have **clear ownership**, typically assigned to specific Development Teams and Business Organizational Units, ensuring accountability and clear decision-making authority. In hierarchical module structures, ownership can be explicitly defined at any level, and it naturally propagates down to nested modules unless overridden at a lower level.

To help express the architectural intent and boundaries of modules, they can be tagged (see [Tagging System](#tagging-system) section). These tags can reflect different architectural approaches and patterns:

* Traditional Architecture:
  * Feature Module - modules organized around specific features
  * Internal Module - modules not exposed to other parts of the system

* Domain-Driven Design:
  * Bounded Context - modules representing distinct domain boundaries
  * Shared Kernel - modules shared between multiple bounded contexts
  * Anti-corruption Layer - modules that translate between different bounded contexts
  * Open Host Service - modules that provide standardized interfaces


**Relations:**

* contains Domain Object
* contains Domain Behavior
* contains Domain Module (nested)
* is owned by Development Team
* is owned by Business Organizational Unit

---

### Domain Object

Domain Objects are the **fundamental building blocks** of your system's domain model. They encapsulate both *data and behavior*. These objects represent real-world concepts, business entities, or abstract ideas from your problem domain. They can be as simple as a value object holding a single piece of information, or as complex as an entity managing its own lifecycle and business rules.

Domain Objects may include or be composed of Domain Behaviors, making them **active participants** in your system rather than just data containers. They use other Domain Objects to fulfill their responsibilities, creating a network of collaborating objects that model your business domain. These objects are used by Domain Behaviors to perform operations, but they can also contain their own business logic and validation rules.

The concept of Domain Objects is deeply rooted in software development practices, where they are typically implemented as classes in object-oriented languages. They can be tagged (see [Tagging System](#tagging-system) section) to indicate their architectural roles and patterns. Common examples include:

* Traditional Architecture:
  * Entity - objects with identity and lifecycle
  * Service - objects providing business operations
  * Repository - objects managing persistence
  * Data Transfer Object (DTO) - objects for data exchange

* Domain-Driven Design:
  * Aggregate Root - objects ensuring consistency boundaries
  * Entity - objects with unique identity
  * Value Object - immutable objects with no identity
  * Domain Service - objects for operations spanning multiple entities
  * Repository - objects for persistence abstraction
  * Factory - objects for complex object creation
  * Specification - objects for complex queries

* Functional Programming (including patterns inspired by Scott Wlaschin's "Domain Modeling made Functional"):
  * Monad - objects for handling effects and computations
  * Functor - objects that can be mapped over
  * Effect - objects representing side effects
  * Workflow - objects representing business processes with defined steps
  * State Machine - objects managing state transitions
  * Result - objects representing success/failure outcomes
  * Choice - objects representing discriminated unions
  * Constrained Type - objects with validation rules
  * Smart Constructor - objects with controlled instantiation

**Relations:**

* contains Domain Behavior
* uses Domain Object
* is used by Domain Behavior
* belongs to Domain Module

---

### Domain Behavior

Domain Behaviors are the **active elements** of your system that implement functionality and business logic. They represent operations, transformations, or processes that can exist in two ways:
* As **independent, standalone operations** that can be invoked directly
* As part of Domain Objects, where they implement the object's behavior and business rules

This *dual nature* makes behaviors particularly versatile and allows them to fit into various architectural styles - from pure functional programming where they are first-class citizens, through object-oriented approaches where they might be methods of objects, to service-oriented architectures where they represent business operations.

Domain Behaviors may depend on Domain Objects and invoke other Domain Behaviors, creating a network of operations that implement your business processes. They expose their functionality externally, typically through APIs, making them the **primary interface** between different parts of your system. This exposure can be controlled through tagging (see [Tagging System](#tagging-system) section) to indicate their role in the system architecture. Common tags include:

* Entry Point - behaviors that serve as the system's external interface
* Module Interface - behaviors that expose module functionality to other modules
* Internal Interface - behaviors used within a module's implementation
* Event Handler - behaviors that process system events
* Command Handler - behaviors that execute specific commands



**Relations:**

* uses Domain Object
* invokes Domain Behavior
* is exposed by API
* belongs to Domain Module / Domain Object / Business Process

---

### Business Process

Business Processes represent structured business workflows composed of sequences of Domain Behaviors, executed either manually by users or automatically by the system.

**Relations:**

* contains Domain Behavior
* is owned by Business Organizational Unit

---

## Technology

### Deployment Container

Deployment Containers represent runtime environments (e.g., servers, VMs, Kubernetes clusters, cloud services). They may contain other Deployment Containers and host Deployable Units.

**Relations:**

* contains Deployment Container
* hosts Deployable Unit

---

### Deployable Unit

Deployable Units are independently deployable software components (e.g., applications, services, functions). They are hosted in Deployment Containers and expose their features via APIs. They also contain Domain Objects and Domain Behaviors.

**Relations:**

* is hosted by Deployment Container
* contains Domain Object
* contains Domain Behavior
* provides API

---

### API

APIs provide access to functionalities offered by Deployable Units. They enable external systems or users to invoke Domain Behaviors.

**Relations:**

* is provided by Deployable Unit
* invokes Domain Behavior

---

## People

### Development Team

Development Teams consist of technical roles (e.g., developers, analysts, testers). They are responsible for building and maintaining Domain Modules and Deployment Containers.

**Relations:**

* owns Domain Module
* owns Deployment Container

---

### Business Organizational Unit

Business Organizational Units represent departments or organizational entities driving requirements and strategy. They own Domain Modules and Business Processes and may contain other Business Units.

**Relations:**

* owns Domain Module
* owns Business Process
* contains Business Organizational Unit

---

### Actor

Actors are system users who interact with Domain Behaviors as part of executing business tasks.

**Relations:**

* uses Domain Behavior

---

## Tagging System

The P3 Model includes a flexible tagging system that allows for architectural style adaptation. Unlike rigid architectural frameworks, the tagging system in P3 is completely customizable - you can define your own tags based on your project's specific needs, architectural style, or team preferences. The examples below are just common patterns, but you are free to create your own tagging scheme that best fits your context.

This flexibility enables the model to align with various architectural approaches such as:

* Traditional layered architecture (Entities, Services, Repositories)
* Domain-Driven Design (Aggregates, Value Objects, Bounded Contexts)
* Functional programming (Pure Functions, Monads, Effects)
* Event-driven architecture (Event Handlers, Command Handlers)
* Microservices (Service Boundaries, API Gateways)
* Modular Monolith (Module Interfaces, Internal Modules)

Tags can be used to:
* Mark architectural roles and patterns
* Highlight cross-cutting concerns
* Mark entry points and public APIs

This tagging capability makes the P3 Model adaptable to different architectural styles while maintaining its core structure. You can start with a minimal set of tags and evolve them as your understanding of the system grows, or adopt a comprehensive tagging scheme from the beginning if your team already has established patterns.

---