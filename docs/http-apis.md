---
sidebar_position: 11
---

# HTTP APIs

## Definitions

- **Resource** - An important thingy you want to expose through your API
- **URI** - a name for a resource (Uniform Resource Identifier)
- **METHOD** - Resources have a fixed set of methods. You can't make them up. See below.
- **Representation** - A projection of the state of a resource at a particular point in time.
- **Media Type** - A specific format for a representation, like `application/json`, `text/html`, etc.

## Http Resources

Two basic categories.

- **Document** - Represents a specific instance of a resource. e.g. `/customers/bob-smith`
- **Collection** - Represents a group of related resources. e.g. `/customers`

Documents are usually _subordinate_ resources to a collection, but documents can also have subordinate resources that are either documents
or collections.

Examples:

`/customers/bob-smith/address` - the address data for Bob Smith.
`/customers/bob-smith/sales-rep` - Bob's sales representative (could be an alias to `/employees/jill-jones`)

Collection resources can be filtered using a query string argument:

- `GET /customers` - returns all customers
- `GET /customers?state=KY` - returns just the customers in Kentucky

## Http Methods

| Method | Description                                    | Resource Type | Example                                  | Safe  | Idempotent | Cacheable |
| ------ | ---------------------------------------------- | ------------- | ---------------------------------------- | ----- | ---------- | --------- |
| GET    | Retreive a representation                      | Document      | `GET /customers/bob-smith`               | True  | True       | True      |
| GET    | Retreive a representation                      | Collection    | `GET /customers/`                        | True  | True       | True      |
| POST   | Submit an Entity For Processing                | Document      | `POST /customers/bob-smith/credit`       | False | False      | False     |
| POST   | Consider Adding this as a subordinate resource | Collection    | `POST /customers`                        | False | False      | False\*   |
| PUT    | Replace (or upsert) this document              | Document      | `PUT /customers/bob-smith/email-address` | False | True       | False     |
| PUT    | Replace this collection                        | Collection    | `PUT /customers`                         | False | True       | False     |
| DELETE | Remove this document                           | Document      | `DELETE /customers/bob-smith/`           | False | True       | False     |
| DELETE | Remove this collection                         | Collection    | `DELETE /customers/`                     | False | True       | False     |

:::note
Rarely do you support `DELETE` or `PUT` on a collection, and rarely do you support `POST` on a document
:::

### Properties

- **Safe** - means there are no "side effects" - nothing about the business changes because of this operation.
- **Idempotent** - Doing it multiple times has the same effect as doing it once.
- **Cacheable** - Responses from this operation should have cache headers indicating their reuse constraints.

### Threading in APIs

![API Threading](/img/threading-in-apis.excalidraw.svg)
