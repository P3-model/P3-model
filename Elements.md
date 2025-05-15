# P3 Model

Here you can find description of all P3 Model *Elements* and *Relations*.

These *Elements* are divided int three perspectives:

- *Domain* - what business concepts are implemented in the system
- *Technology* - what technical solutions are used to run the system
- *People* - how people develop, maintain and use the system

## Domain

### Domain Building Block

Domain Building Blocks represent meaningful business concepts. They encapsulate business logic, rules, and domain data. They can take the form of tactical DDD Building BLocks (like Aggregates, Value Objects or Domain Services) or traditional, simpler Entities and Services.

Domain Building Blocks exist within Domain Modules, expressing clear domain relationships and dependencies. They interact directly with other Domain Building Blocks and support Process Steps.

From a technical perspective, Domain Building Blocks are packaged into Deployable Units.

**Relations:**

- belongs to Domain Module
- depends on Domain Building Block
- is dependency for Domain Building Block
- is dependency for Process Step
- is packaged into Deployable Unit

------

### Domain Module

Domain Modules group closely related domain concepts into cohesive logical units.

Domain Modules maintain hierarchical structures to reflect the complexity and granularity of domain organization, clearly delineating responsibility within the domain itself.

If you are using DDD top-level modules usually correspond to Bounded Contexts, while submodules might represent Modules in DDD meaning.

Organizationally, each Domain Module has clearly defined ownership by Development Teams and Business Organizational Units, facilitating alignment between technical delivery and business objectives.

**Relations:**

- contains Domain Module
- has parent Domain Module
- is owned by Development Team
- is owned by Business Organizational Unit
- contains Process Step
- contains Domain Building Block

------

### Process

Processes represent business workflows aimed at achieving defined business outcomes. A Process consists of ordered Process Steps, involving manual user interaction or automated system actions.

From a business perspective, Processes are explicitly owned and managed by Business Organizational Units, ensuring alignment with strategic objectives and clear accountability for process execution.

**Relations:**

- contains Process Step
- is owned by Business Organizational Unit

------

### Process Step

A Process Step is a single, atomic action within a broader Process. Each step can be reused across different Processes and may trigger subsequent steps automatically. 

Process Step coordinates various Domain Building Blocks.

In technical terms, Process Steps can be exposed externally via APIs, allowing integration with other systems or external interactions.

From the user perspective, manual Process Steps involve direct interaction by Actors (end-users).

**Relations:**

- belongs to Domain Module
- depends on Domain Building Block
- is part of Process
- is used by Actor
- is exposed by API

------

## Technology

### Deployment Container

Deployment Containers represent environments into which Deployable Units are deployed. These environments include physical hardware (bare metal), virtual machines, Kubernetes clusters, database servers, message queues, cloud-managed services and others.

Deployment Containers can form hierarchical structures, allowing flexible infrastructure organization tailored to operational and organizational needs.

Each Deployment Container can hosts Deployable Units and/or contains other Deployment Containers.

**Relations:**

- contains Deployment Container
- is contained by Deployment Container
- hosts Deployable Unit

------

### Deployable Unit

Deployable Units are independently deployable software components such as standalone applications, database instances, cloud functions (lambdas), or messaging system configuration.

Deployable Units operate within Deployment Containers, clearly defining runtime contexts.

From a domain perspective, Deployable Units contain specific Domain Building Blocks.

Technically, Deployable Units expose their functionalities through APIs, enabling external integration.

**Relations:**

- executes in Deployment Container
- provides API
- contains Domain Building Block

------

### API

APIs are technical mechanisms for accessing functionalities provided by Deployable Units. Common API implementations include HTTP endpoints or queue-based message handlers.

APIs enable technical interaction with Deployable Units, providing well-defined integration points for system-to-system communication.

From the business perspective, APIs expose specific Process Steps, clearly linking technical interfaces to business capabilities.

**Relations:**

- is provided by Deployable Unit
- exposes Process Step

------

## People

### Development Team

Development Teams consist of technical and analytical roles such as developers, architects, analysts, testers, and product owners, collaboratively building and maintaining domain logic and the associated technical solutions.

Development Teams have explicit ownership of Domain Modules, clearly defining technical responsibility and scope of work.

**Relations:**

- contains Development Team Member
- owns Domain Module

------

### Development Team Member

A Development Team Member is an individual occupying a technical or analytical role within a Development Team, directly contributing to the development and maintenance of domain and technical solutions.

Each team member is explicitly assigned to a Development Team, clarifying organizational structure and team composition.

**Relations:**

- belongs to Development Team

------

### Business Organizational Unit

Business Organizational Units represent formal organizational entities (e.g., departments or divisions) responsible for business-driven requirements, oversight, and strategy related to system development.

Business Organizational Units clearly own Domain Modules and Processes, providing transparent accountability and governance for business requirements and related software functionality.

Organizationally, they can have hierarchical relationships reflecting the broader organizational structure.

**Relations:**

- contains Business Organizational Unit
- has parent Business Organizational Unit
- owns Domain Module
- owns Process

------

### Actor

Actors are end-users who interact directly with the system, performing manual steps within business Processes to accomplish specific business goals.

Actors explicitly execute manual Process Steps, directly contributing to achieving defined business outcomes through their interaction with the system.

**Relations:**

- uses Process Step
