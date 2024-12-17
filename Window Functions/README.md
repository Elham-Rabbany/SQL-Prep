# Window Functions in SQL  

Window functions allow you to perform aggregate calculations over a specific "window" of rows without collapsing the data, unlike `GROUP BY`. They are powerful for analysis, ranking, and comparing rows within a dataset.

---

## Table of Contents  

1. [What are Window Functions?](#what-are-window-functions)  
2. [Aggregates with PARTITION BY](#aggregates-with-partition-by)  
3. [Ranking Functions](#ranking-functions)  
4. [LAG and LEAD Functions](#lag-and-lead-functions)  
5. [Summary of Key Window Functions](#summary-of-key-window-functions)  

---

## 1. What are Window Functions?  

- **Window Functions** operate on a "window frame" — a set of rows related to the current row.  
- **Key Benefits**:  
   - Perform aggregate calculations while retaining row-level details.  
   - Combine results like totals, ranks, and differences without collapsing data.  
- **Syntax**: The `OVER()` clause defines the window frame.  
   - `PARTITION BY`: Groups rows into partitions for calculation.  
   - `ORDER BY`: Defines row order within each partition.  

---

## 2. Aggregates with PARTITION BY  

- Use **PARTITION BY** to group rows and calculate aggregate values while retaining details.  
- **Example Use Case**:  
   - Calculate totals per group (e.g., country, day, or month) while viewing individual rows.  

**Key Points**:  
- Works similarly to `GROUP BY`, but rows are not collapsed.  
- Supports aggregates like `SUM()`, `COUNT()`, and `AVG()`.  

---

## 3. Ranking Functions  

SQL window functions can assign ranks to rows within a partition using `ORDER BY`.  

| **Function**     | **Description**                                                 |  
|------------------|-----------------------------------------------------------------|  
| **ROW_NUMBER()** | Assigns a unique sequential number to each row.                 |  
| **RANK()**       | Assigns ranks, with ties receiving the same rank and skipping numbers. |  
| **DENSE_RANK()** | Assigns ranks without skipping numbers when ties exist.         |  

**When to Use**:  
- Use `RANK` to account for ties while skipping ranks.  
- Use `DENSE_RANK` to avoid skipping ranks in tied results.  
- Use `ROW_NUMBER` when no ties are involved.  

**Best Use Case**: Ranking results, such as identifying top performers or joint positions.  

---

## 4. LAG and LEAD Functions  

The `LAG` and `LEAD` functions compare rows to preceding or succeeding rows in the dataset.

- **LAG**: Retrieves a value from the **previous row**.  
- **LEAD**: Retrieves a value from the **next row**.  

### Use Case:  
- Compare monthly sales or calculate differences between consecutive rows.  

**Example Workflow**:  
1. Use `LAG()` to fetch the previous row's value.  
2. Calculate the difference between the current row and the previous row.  

---

## 5. Summary of Key Window Functions  

| **Function**          | **Purpose**                                  | **Common Keywords**                  |  
|------------------------|---------------------------------------------|--------------------------------------|  
| **PARTITION BY**       | Defines groups (windows) for calculations. | `OVER (PARTITION BY column)`         |  
| **ROW_NUMBER()**       | Assigns a sequential row number.            | `ORDER BY`                           |  
| **RANK()**             | Ranks rows with ties, skips ranks.          | `ORDER BY`                           |  
| **DENSE_RANK()**       | Ranks rows without skipping ranks.          | `ORDER BY`                           |  
| **LAG()**              |
