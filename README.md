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
