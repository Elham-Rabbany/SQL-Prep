# SQL Maths

This section introduces **SQL Maths** concepts to perform calculations, transformations, and value manipulations on your data using arithmetic operators and mathematical functions.

---

## Table of Contents  

1. [Arithmetic Operators](#arithmetic-operators)  
2. [Math Functions](#math-functions)  
3. [Combining Maths with Queries](#combining-maths-with-queries)  

---

## 1. Arithmetic Operators  

Arithmetic operators are used to perform fundamental mathematical operations on numeric values:  

- **Addition (`+`)**: Add two or more values.  
- **Subtraction (`-`)**: Subtract one value from another.  
- **Multiplication (`*`)**: Multiply values together.  
- **Division (`/`)**: Divide one value by another.  
- **Modulus (`%`)**: Return the remainder of a division operation.  

### Use Cases:  

- **Static Calculations**: Perform direct arithmetic.  
  Example: Adding a fixed value.  
- **Column Operations**: Modify column values directly, e.g., applying discounts.  
- **Multi-Column Calculations**: Calculate results using values from multiple columns.  

---

## 2. Math Functions  

SQL offers a range of mathematical functions to perform more complex calculations.  

| **Function**      | **Description**                                     | **Example**                    |
|--------------------|-----------------------------------------------------|--------------------------------|
| **ABS()**         | Returns the absolute (positive) value of a number.  | `SELECT ABS(-4); -- Outputs 4` |
| **CEIL()**        | Rounds up to the nearest whole number.              | `SELECT CEIL(5.2); -- Outputs 6` |
| **FLOOR()**       | Rounds down to the nearest whole number.            | `SELECT FLOOR(8.9); -- Outputs 8` |
| **POW(x, y)**     | Raises a base (`x`) to the power of an exponent (`y`). | `SELECT POW(10, 2); -- Outputs 100` |
| **ROUND(x, d)**   | Rounds a number (`x`) to a specified number of decimal places (`d`). | `SELECT ROUND(2.718, 2); -- Outputs 2.72` |

### Use Cases:  

- **Rounding Values**: Adjust numeric results for presentation or reporting.  
- **Exponential Calculations**: Use `POW()` to calculate powers (e.g., square or cube values).  
- **Absolute Values**: Ensure all numbers are positive using `ABS()`.  
- **Precision Control**: Combine `CEIL()` or `FLOOR()` to control rounding behavior.  

---

## 3. Combining Maths with Queries  

Mathematical operations and functions can be applied in real-world queries for data transformation and analysis.

### Examples of Real-World Applications:

1. **Calculating Total Price**: Multiply `UnitPrice` by `Quantity` to calculate the total price of an order.  
   ```sql
   SELECT 
       UnitPrice, 
       Quantity, 
       UnitPrice * Quantity AS TotalPrice
   FROM Order_Details;
