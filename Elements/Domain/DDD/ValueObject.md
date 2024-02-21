# Value Object *[draft]*

## Description

// TODO: Add description

## Examples

- *Money* - decimal value in certain currency with restricted set of arithmetic operations
- *Tax Id* - business identifier for tax purposes
- *Order Id* - technical identifier (e.g. int or UUID) for orders
- *Offer* - offer in some domains can by only value that is calculated to compare it with other offers or create order base on it

## Attributes

| Attribute name    | Data Type | Description                                                                            |
|-------------------|-----------|----------------------------------------------------------------------------------------|
| Id                | string    | Unique identifier of the Domain Building Block e.g. *domainbuildingblock\|sales.taxid* |
| Name              | string    | Name of the Building Block e.g. *Tax Id*                                               |
| Short description | string    |                                                                                        |

## Relations

| Relation name     | Related Element | Type        | Description |
|-------------------|-----------------|-------------|-------------|
| Depends on        | Building Block  | one to many |             |
| Is implemented by | Code Structure  | one to many |             |

## External resources

- [DDD Reference](https://www.domainlanguage.com/ddd/reference/)