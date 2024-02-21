# Building Block *[draft]*

## Description

*Building Block is a model for some domain concept.* It can model:
- a thing like Car or Box
- a concept like Tax Id
- a behavior like Discount Calculator

*There can be more precise types of Building Blocks* like Value Object or Process Step. These more precise types have different meanings and can have additional attributes and relations.

*Building Blocks are atoms for Domain Model.* Every Element that is below Building Block in Domain Perspective like Behaviour or Rule have to me associated with some Building Block. Every Element that is above Building Block in Domain Perspective like Domain Module is a composition of Building Blocks.

*Building Blocks are not a design patterns like patters from GoF.*

## Aliases

- DDD Building Block

## Examples

// TODO: Add examples

## Attributes

| Attribute name    | Data Type | Description                                                                                   |
|-------------------|-----------|-----------------------------------------------------------------------------------------------|
| Id                | string    | Unique identifier of the Domain Building Block e.g. *domainbuildingblock\|sales.orders.order* |
| Name              | string    | Name of the Building Block e.g. *Order*                                                       |
| Short description | string    |                                                                                               |

## Relations

| Relation name     | Related Element | Type        | Description |
|-------------------|-----------------|-------------|-------------|
| Depends on        | Building Block  | one to many |             |
| Is implemented by | Code Structure  | one to many |             |

## Children

- [Process Step](ProcessStep.md)
- DDD
    - [Value Object](DDD/ValueObject.md)