# Overloaded Inventory Manager

You are tasked with creating an ASP.NET Core MVC application that manages products held in a store's inventory.

Each inventory item should contain a SKU, product name, unit price, and quantity. The application should support common inventory operations and comparisons through operator overloading and method overriding.

## Getting Started

Create an ASP.NET Core MVC application named `OverloadedInventoryManager`.

Use an in-memory collection or repository to store the data while the application is running. A database is not required for this activity.

Seed the application with a few inventory items so that the features can be demonstrated immediately.

## Inventory Item

Create an `InventoryItem` model with the following information:
- ID
- SKU
- Product name
- Unit price
- Quantity
- Total stock value

The total stock value should be calculated from the unit price and quantity. It should not be entered separately by the user.

## Object Equality

Two inventory item objects should be treated as the same product when their SKUs match. The SKU comparison should not be case-sensitive.

For example, `MOU101` and `mou101` should represent the same product.

Override and implement the following:
- `Equals`
- `GetHashCode`
- `ToString`
- `IEquatable<InventoryItem>`

## Operator Overloading

Overload the following operators:

### Arithmetic Operations

- `+` should combine the quantities of two matching inventory items.
- `-` should remove the quantity of one matching inventory item from another.
- `++` should increase the quantity by one.
- `--` should decrease the quantity by one.

The arithmetic operators should return new objects rather than unexpectedly changing the original objects.

Items may only be added or subtracted when their SKU, name, and unit price match. The quantity may never become negative.

### Comparison Operations

- `==` should determine whether two objects represent the same product.
- `!=` should determine whether two objects represent different products.
- `<` should compare the total stock values of two inventory items.
- `>` should compare the total stock values of two inventory items.

## App Features

The application should allow the user to:

- View all inventory items.
- View the details of an inventory item.
- Create an inventory item.
- Edit an inventory item.
- Increase stock using the overloaded `++` operator.
- Decrease stock using the overloaded `--` operator.
- Remove a selected quantity using the overloaded `-` operator.
- Combine matching inventory records using the overloaded `+` operator.
- Compare two selected items using `==`, `!=`, `<`, `>`, and `Equals`.