# SQL Joins Examples

This repository contains SQL queries demonstrating different types of joins using a sample database schema.

## Queries

### 1. Employee-Office Information (INNER JOIN)
Retrieves employee details along with their office information using an INNER JOIN between the employees and offices tables.

**Query:**
```sql
SELECT 
    e.firstName,
    e.lastName,
    e.email,
    e.officeCode
FROM 
    employees e
INNER JOIN 
    offices o
ON 
    e.officeCode = o.officeCode;
```

### 2. Product Information (LEFT JOIN)
Gets product details including vendor and product line information using a LEFT JOIN between products and productlines tables.

**Query:**
```sql
SELECT 
    p.productName,
    p.productVendor,
    p.productLine
FROM 
    products p
LEFT JOIN 
    productlines pl
ON 
    p.productLine = pl.productLine;
```

### 3. Order Details (RIGHT JOIN)
Retrieves order information with customer details using a RIGHT JOIN between customers and orders tables, limited to the first 10 results.

**Query:**
```sql
SELECT 
    o.orderDate,
    o.shippedDate,
    o.status,
    o.customerNumber
FROM 
    customers c
RIGHT JOIN 
    orders o
ON 
    c.customerNumber = o.customerNumber
LIMIT 10;
```

## Database Schema Requirements

These queries assume the following tables exist in the database:

- **employees**: Contains employee information with officeCode field
- **offices**: Contains office details with officeCode field
- **products**: Contains product information with productLine field
- **productlines**: Contains product line details
- **customers**: Contains customer information with customerNumber field
- **orders**: Contains order details with customerNumber field

## Usage

1. Ensure you have a SQL database with the required tables and data
2. Execute the queries in your SQL client or application
3. Modify the queries as needed for your specific database structure

## Join Types Explained

- **INNER JOIN**: Returns records that have matching values in both tables
- **LEFT JOIN**: Returns all records from the left table, and matched records from the right table
- **RIGHT JOIN**: Returns all records from the right table, and matched records from the left table

## License

This code is provided as an educational example. Feel free to use and modify as needed.
