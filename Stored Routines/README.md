# Stored Routines in SQL  

Stored routines simplify database tasks and logic using **Views**, **Stored Procedures**, and **Stored Functions**.

---

## 1. Stored Views  

- **What**: Virtual tables that store predefined queries.  
- **Purpose**: Simplify complex queries and improve data access consistency.  
- **Use Case**: Filter or organize data without rewriting queries.
  
**Key Keywords**: 
- **CREATE VIEW**: Create a virtual table based on a query.  
- **AS**: Define the query for the view.  
- **SELECT**: Query the view like a regular table.  
- **FROM**: Specify the base table(s) for the view.  

---

## 2. Stored Procedures  

- **What**: Pre-written SQL statements that automate tasks.  
- **Purpose**: Perform actions like data insertion, updates, or deletions.  
- **Use Case**: Automate workflows and enforce business rules.

**Key Keywords**: 

- **CREATE PROCEDURE**: Create a stored procedure.  
- **DELIMITER**: Change the statement delimiter when defining procedures.  
- **BEGIN** / **END**: Enclose the procedure logic.  
- **IN** / **OUT** / **INOUT**: Define input and output parameters.  
- **CALL**: Execute a stored procedure.  
- **DECLARE**: Declare variables within a procedure.  

  ### **Syntax**:  
```sql
CREATE VIEW ViewName AS
SELECT column1, column2, ...
FROM TableName
WHERE condition;´´´´

---

## 3. Stored Functions  

- **What**: Encapsulated logic that returns a single value.  
- **Purpose**: Simplify calculations and improve reusability.  
- **Use Case**: Frequently used operations like totals, discounts, or taxes.  

**Key Keywords**:

## 3. Stored Functions  
- **CREATE FUNCTION**: Create a stored function.  
- **RETURNS**: Specify the return data type.  
- **DETERMINISTIC** / **NOT DETERMINISTIC**: Define whether the function always returns the same output for the same input.  
- **BEGIN** / **END**: Enclose the function logic.  
- **RETURN**: Specify the value to return from the function.  
- **DECLARE**: Declare variables within the function. 

---

## Summary of Differences  

| **Feature**          | **Views**       | **Stored Procedures** | **Stored Functions** |  
|-----------------------|----------------|-----------------------|----------------------|  
| **Output**           | Virtual table.  | Result set or status. | Single value.        |  
| **Input Parameters**  | No.            | Yes.                  | Yes.                 |  
| **Data Modification** | No.            | Yes.                  | No.                  |  

