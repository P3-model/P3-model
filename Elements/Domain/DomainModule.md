# Domain Module *[draft]*

## Description

**Domain Module is a separated, cohesive set of tightly connected building blocks that models business terms, behaviors
and rules.**

**Domain Module is not grouping by pattern or technical concerns.** Entities, Value Objects, Repositories, Services are
not good names for Domain Modules.

**Domain Modules can form a hierarchy.** One module can contains zero, one or many other modules. It's useful if domain
is rather large and complex and can be naturally divided into smaller areas hierarchically arranged. Sometimes this
hierarchy cen mimic enterprise organizational structure but it doesn't have to be one-to-one relation. It's more about
business capabilities and responsibilities than about organizational structure.

**Domain Module contains [Domain Building Blocks](BuildingBlock.md)**. Each Building Block belongs to only one Domain
Module. Building Blocks inside single Module should be more tightly connected than Building Blocks from different Modules. Building Blocks from Modules closer in hierarchy should be more tightly connected than Building Blocks from Modules further in hierarchy.

## Aliases

- DDD Module

## Examples

- *Sales* - top level module for all business concepts related to sales activity
- *Pricing* - a part of Sales module that is responsible for pricing and discounting
- *Discounts* - a part of Pricing module that is responsible for calculating discounts

## Attributes

| Attribute name | Data Type | Description                                         |
|----------------|-----------|-----------------------------------------------------|
| Id             | string    | Unique identifier of the Domain Module e.g. *Sales* |
| Name           | string    | Name of the Domain Module e.g. *Sales*              |

## Relations

| Relation name     | Related Element | Type        | Description |
|-------------------|-----------------|-------------|-------------|
| Contains          | Domain Module   | one to many |             |
| Contains          | Building Block  | one to many |             |
| Is deployed in    | Deployable Unit | many to one |             |
| Is implemented by | Code Structure  | one to many |             |
