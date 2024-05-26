# BookShop Management System

## Overview

The BookShop Management System is a C++ console application designed to help manage the operations of a bookshop efficiently. This system provides functionality for managing books, suppliers, purchases, employees, members, and sales.

## Features

- **Book Management**: Add, view, and manage book details.
- **Supplier Management**: Store and retrieve information about book suppliers.
- **Purchase Management**: Record and track purchase orders.
- **Employee Management**: Maintain records of employees.
- **Member Management**: Manage membership details.
- **Sales Management**: Record sales transactions and generate invoices.

## Requirements

- C++ compiler
- MySQL database server
- MySQL connector for C++

## Database Schema

The database consists of six tables:

1. **Books**
   - `id` (int): Primary key.
   - `name` (string): Name of the book.
   - `auth` (string): Author of the book.
   - `price` (int): Price of the book.
   - `qty` (int): Quantity in stock.

2. **Suppliers**
   - `id` (int): Primary key.
   - `name` (string): Supplier's name.
   - `phn` (long int): Phone number.
   - `addr_line1` (string): Address line 1.
   - `addr_line2` (string): Address line 2.
   - `addr_city` (string): City.
   - `addr_state` (string): State.

3. **Purchases**
   - `ord_id` (int): Primary key.
   - `book_id` (int): Foreign key referencing `Books(id)`.
   - `sup_id` (int): Foreign key referencing `Suppliers(id)`.
   - `qty` (int): Quantity ordered.
   - `dt_ordered` (date): Date of order.
   - `eta` (int): Estimated time of arrival.
   - `received` (char): Status of the order (T - in transit, C - cancelled, F - fulfilled).
   - `inv` (int): Invoice number.

4. **Employees**
   - `id` (int): Primary key.
   - `name` (string): Employee's name.
   - `addr_line1` (string): Address line 1.
   - `addr_line2` (string): Address line 2.
   - `addr_city` (string): City.
   - `addr_state` (string): State.
   - `phn` (long int): Phone number.
   - `date_of_joining` (date): Date of joining.
   - `salary` (long int): Salary.
   - `mgr_status` (string): Manager status (T - true, F - false).

5. **Members**
   - `id` (int): Primary key.
   - `name` (string): Member's name.
   - `addr_line1` (string): Address line 1.
   - `addr_line2` (string): Address line 2.
   - `addr_city` (string): City.
   - `addr_state` (string): State.
   - `phn` (long int): Phone number.
   - `beg_date` (date): Membership start date.
   - `end_date` (date): Membership end date.
   - `valid` (string): Membership validity status.

6. **Sales**
   - `invoice_id` (int): Primary key.
   - `member_id` (int): Foreign key referencing `Members(id)`.
   - `book_id` (int): Foreign key referencing `Books(id)`.
   - `qty` (int): Quantity sold.
   - `amount` (int): Total amount of the transaction.
   - `date_s` (date): Date of the sale.

