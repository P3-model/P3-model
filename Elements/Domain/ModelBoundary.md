# Model Boundary *[draft]*

## Description

**Model Boundary is a boundary that separate a set of domain terms, behaviors and rules.** All elements within this boundary constitute separate model. Models from different boundaries should be as loosely coupled as possible. To integrate separate models explicitly defined public contract should be established. 

**Within Model Boundary each term has precise and unambiguous meaning.** The same term in a different boundary can have different meaning. Integration of two models requires explicit translation of terms.

**Defining Model Boundaries is an alternative to one canonical or corporate model for the entire domain.** Such one big model rarely can be unambiguous. As Eric Evans says: *total unification of the domain model for a large system will not be feasible or cost-effective*. Moreover several separate models better reflects business reality. Let's take for example business concept like product from ordinary e-commerce. We have many stakeholder here e.g. client, warehouseman, manager from revenue optimization department or even engineer that handles the complaint process. They do totally different things with a product so they need different behaviors, rules and data. Putting in all into single model is not a good idea. Instead we need separate, specialized models for all different meaning of a product. These models should live in a clearly established boundaries.

## Aliases

- DDD Bounded Context

## Examples

- *Sales* model for ale requirements from Sales department
- *Pricing* model that is owned also by Sales department but has different product meaning and is used by several other models which don't need the rest of the *Sales* model
- *Availability Management* model that doesn't map to any organizational division in the company but provides one of the basic business capabilities needed in many business processes
- *Risk Scoring* model that is used in company's larger financial system and is also sold a separate product for other companies

## Attributes

| Attribute name | Data Type | Description                                                  |
|----------------| --------- | ------------------------------------------------------------ |
| Name           | string    | Name of the Model Boundary e.g. *Sales*                      |
| Decision       | string    | Name of the design decision or link to this decision e.g. *ADR_027* |

## Relations

| Relation name | Related Element | Type        | Description                                                  |
| ------------- | --------------- | ----------- | ------------------------------------------------------------ |
| Contains      | Building Block  | one to many | One Model Boundary contains many Building Blocks. <br />Each Building Block belongs to only one Model Boundary. |