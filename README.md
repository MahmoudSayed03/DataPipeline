# **Sales Data Warehouse**

## **Overview**

This project involves the design and implementation of a data warehouse solution to consolidate and analyze sales data. The data warehouse integrates sales information from multiple sources and organizes it into structured fact and dimension tables, enabling efficient data analysis and reporting.

## **Fact Table: SalesFact**

The **SalesFact** table stores detailed sales data, serving as the central table in the data warehouse.

| **Column**      | **Description**                                                          |
|-----------------|--------------------------------------------------------------------------|
| `RowID`         | Primary Key: Unique identifier for each row in the fact table.           |
| `OrderID`       | Unique identifier for each order.                                        |
| `DateKey`       | Foreign Key: References the `DateKey` in the `DateDim` table.            |
| `CustomerKey`   | Foreign Key: References the `CustomerKey` in the `CustomerDim` table.    |
| `ProductKey`    | Foreign Key: References the `ProductKey` in the `ProductDim` table.      |
| `GeographyKey`  | Foreign Key: References the `GeographyKey` in the `GeographyDim` table.  |
| `ShipModeKey`   | Foreign Key: References the `ShipModeKey` in the `ShipModeDim` table.    |
| `Sales`         | Sales amount for the order.                                              |
| `Quantity`      | Quantity of products sold.                                               |
| `Discount`      | Discount applied to the order.                                           |
| `Profit`        | Profit from the order.                                                   |

## **Dimension Tables**

### **DateDim Table**

Stores information related to dates.

| **Column**      | **Description**                                             |
|-----------------|-------------------------------------------------------------|
| `DateKey`       | Primary Key: Unique identifier for the date.                |
| `OrderDate`     | Date the order was placed.                                   |
| `ShipDate`      | Date the order was shipped.                                  |
| `Year`          | Year component of the order date.                            |
| `Quarter`       | Quarter component of the order date.                         |
| `Month`         | Month component of the order date.                           |
| `Day`           | Day component of the order date.                             |
| `DayOfWeek`     | Day of the week component of the order date.                 |

### **CustomerDim Table**

Stores information related to customers.

| **Column**      | **Description**                                             |
|-----------------|-------------------------------------------------------------|
| `CustomerKey`   | Primary Key: Unique identifier for the customer.            |
| `CustomerID`    | Unique identifier for the customer.                         |
| `CustomerName`  | Name of the customer.                                       |
| `Segment`       | Segment to which the customer belongs.                      |

### **ProductDim Table**

Stores information related to products.

| **Column**      | **Description**                                             |
|-----------------|-------------------------------------------------------------|
| `ProductKey`    | Primary Key: Unique identifier for the product.             |
| `ProductID`     | Unique identifier for the product.                          |
| `Category`      | Category of the product.                                    |
| `SubCategory`   | Sub-category of the product.                                |
| `ProductName`   | Name of the product.                                        |

### **GeographyDim Table**

Stores geographical information related to orders.

| **Column**      | **Description**                                             |
|-----------------|-------------------------------------------------------------|
| `GeographyKey`  | Primary Key: Unique identifier for the geographical area.   |
| `Country`       | Country where the order was placed.                         |
| `City`          | City where the order was placed.                            |
| `State`         | State where the order was placed.                           |
| `PostalCode`    | Postal code of the order.                                   |
| `Region`        | Region where the order was placed.                          |

### **ShipModeDim Table**

Stores information related to shipping modes.

| **Column**      | **Description**                                             |
|-----------------|-------------------------------------------------------------|
| `ShipModeKey`   | Primary Key: Unique identifier for the shipping mode.       |
| `ShipMode`      | Name or description of the shipping mode (e.g., Standard, Express, Two-Day). |
