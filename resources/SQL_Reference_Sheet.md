# SQL Reference Sheet for Beginners

A quick-reference guide for learners using **SQL** in an *Introduction to Databases* course. This guide explains fundamental terminology, key structures, and relationships used when working with relational databases.

---

## Understanding Databases

A **database** is an organized collection of structured data that can be easily accessed, managed, and updated.

---

## Core Elements of a Database

| **Term** | **Definition** | **Example** |
|-----------|----------------|--------------|
| **Table** | A structure that stores data in rows and columns, similar to a spreadsheet. | Table: `Customer` |
| **Column (Field)** | Defines an attribute of the data and specifies its data type. | Column: `FirstName VARCHAR(50)` |
| **Row (Record)** | A single entry or instance of data in a table. | `(1, 'John', 'Doe')` |
| **Primary Key (PK)** | A unique column or combination of columns that identifies each row. | `CustomerID` in Customer table |
| **Foreign Key (FK)** | A column that links data between two tables by referencing a primary key in another table. | `CustomerID` in Invoice table referencing `Customer.CustomerID` |
| **Data Type** | Defines the kind of data a column can store *(numbers, text, dates, etc.)*. | `INT`, `VARCHAR`, `DATE`, `BOOLEAN` |
| **Constraint** | A rule that ensures data integrity and validity within a table. | `NOT NULL`, `UNIQUE`, `CHECK`, `FOREIGN KEY` |

---

## Key Relationships

| **Relationship Type** | **Description** | **Example** |
|------------------------|----------------|--------------|
| **One-to-One** | Each record in one table corresponds to only one record in another. | A user profile table linked to one login record per user. |
| **One-to-Many** | One record in a parent table can relate to many records in a child table. | One customer can have many invoices. |
| **Many-to-Many** | Records in both tables relate to multiple records in the other, managed through a junction table. | Students enrolled in multiple courses, and courses taken by multiple students. |

---

## Common SQL Concepts

| **Concept** | **Description** | **Example** |
|--------------|----------------|--------------|
| **Query** | A command used to retrieve or manipulate data in a database. | `SELECT * FROM Customer;` |
| **Schema** | The structure or blueprint of a database, including tables, columns, relationships, and constraints. | `dbo.Customer` schema in SQL Server |
| **Entity-Relationship Diagram (ERD)** | A visual map of tables, their fields, and how they connect. | Diagram showing `Customer` ↔ `Invoice` relationship |
| **Normalization** | The process of organizing data to reduce redundancy and improve consistency. | Splitting customer address info into a separate `Address` table. |
| **Index** | A database structure that improves the speed of data retrieval. | Index on `Email` column for faster searches. |

---

## Example: Simple Database Structure

### Customer Table

| CustomerID | FirstName | LastName | Email | DateOfBirth |
|-------------|------------|-----------|--------|--------------|
| 1 | John | Doe | john.doe@example.com | 1980-05-15 |

### Invoice Table

| InvoiceID | CustomerID | InvoiceDate | Total |
|------------|-------------|--------------|-------|
| 1001 | 1 | 2026-02-26 | 250.00 |

**Relationship:**  
`Invoice.CustomerID` → references → `Customer.CustomerID`

---
#### Always define clear **primary** and **foreign keys**, choose the correct **data types**, and use **constraints** to maintain consistency.  
---

### Disclaimer
This reference sheet was created for educational purposes as part of a personal learning project. It includes foundational ideas inspired by the *Microsoft SQL Database Foundations* course but is not an official Microsoft publication. All credit for original course concepts belongs to Microsoft and its authors. This document is intended solely as a supplemental study resource for learning SQL and database fundamentals.
