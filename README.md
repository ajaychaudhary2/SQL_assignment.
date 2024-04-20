# SQL_assignment
# SQL Queries README

This repository contains SQL queries SS And the output for managing tables related to technology and product information.

## Files:

- **assignment.sql**: This file contains SQL queries for creating tables, inserting data, and performing select operations on the tables.

## Tables:

### 1. Technology Table
- **Columns**:
  - id: Integer representing the unique identifier for each entry.
  - technology: String representing the technology associated with the entry.

### 2. Product Info Table
- **Columns**:
  - pr_id: Integer representing the unique identifier for each product entry.
  - product: String representing the name of the product.

### 3. Product Info Likes Table
- **Columns**:
  - pr_id: Integer representing the unique identifier for each product entry.
  - user_id: Integer representing the unique identifier for each user who liked the product.
  - like_date: String representing the date when the like was made.

## Queries:

### 1. Finding IDs with Specific Technologies:
- **Query**:
  ```sql
  SELECT id 
  FROM technology
  WHERE technology="python"
  AND id IN (
    SELECT id 
    FROM technology
    WHERE technology = "DS"
    AND id IN (
      SELECT id 
      FROM technology 
      WHERE technology="SQL"
    )
  );
  ```
  This query retrieves IDs that have the technologies "python", "DS", and "SQL".

### 2. Finding Products with No Likes:
- **Query**:
  ```sql
  SELECT pr_id
  FROM product_info
  WHERE pr_id NOT IN (
    SELECT pr_id 
    FROM product_info_likes
  );
  ```
  This query retrieves product IDs that have not received any likes.

## Usage:
- **Database Management System**: These queries are written in SQL and can be executed using a suitable DBMS like MySQL, PostgreSQL, or SQLite.
- **Executing Queries**: Copy the queries from the `assignment.sql` file and execute them in your preferred DBMS environment.

Feel free to modify or extend these queries as needed for your specific requirements.
