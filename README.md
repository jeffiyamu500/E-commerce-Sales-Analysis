# E-commerce-Sales-Analysis 

# Project-Aim
A sample MySQL 8 database for analyzing e-commerce sales. Includes tables for customers, products, orders, and order items.

# Schema-Overview
## Tables

### Customers
- customer_id (INT, PK)
- name (VARCHAR)
- country (VARCHAR)

### Products
- product_id (INT, PK)
- product_name (VARCHAR)
- category (VARCHAR)
- price (DECIMAL)

### Orders
- order_id (INT, PK)
- customer_id (INT, FK)
- order_date (DATE)
- total_amount (DECIMAL)

### Order Items
- order_item_id (INT, PK)
- order_id (INT, FK)
- product_id (INT, FK)
- quantity (INT)

## Sample Query

Calculate total revenue by country:

```sql
SELECT 
  cu.country,
  SUM(oi.quantity * p.price) AS revenue
FROM customers cu
JOIN orders o ON cu.customer_id = o.customer_id
JOIN order_items oi ON o.order_id = oi.order_id
JOIN products p ON oi.product_id = p.product_id
GROUP BY cu.country
ORDER BY revenue DESC;
