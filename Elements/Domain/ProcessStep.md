# Process Step *[draft]*

## Description

**Process Step is one of the Building Blocks that represents single step in a business process.**

TODO: Add more description

## Examples

- *Place Order* step in *Online Ordering* process
- *Calculate Discounts* step in *Online Ordering* process
- *Calculate Taxes* step in *Invoicing* process

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
