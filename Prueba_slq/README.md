link:https://github.com/KevinLise/Prueba_slq_kevin.git

# Justification of the Decisions Made During the Normalization Process

## 1. Initial Structure

Initially, RiwiSupply S.A.S.'s information was stored in a single Excel worksheet called **raw_data**, where supplier, city, warehouse, product, category, purchase, and inventory movement data were all kept in one table.

This structure concentrated all the information in one place, causing data duplication and making information management more difficult.

---

## 2. Identified Problems

During the analysis of the dataset, several issues affecting data quality were identified:

* Some suppliers were registered multiple times with different name formats.
* Some products had inconsistent or duplicated names.
* Product categories were repeated in multiple records.
* Supplier and warehouse cities were repeatedly stored in every inventory movement.
* Warehouse information was duplicated.
* Data redundancy was present because the same information appeared in many rows.
* This structure made updating information difficult and increased the risk of errors in reports.

---

## 3. Transformations Performed

To solve these issues, the first three normal forms were applied.

### First Normal Form (1NF)

Each column was verified to contain only a single value (atomic data), and each row represented a single inventory movement. In addition, a unique identifier (**MovementID**) was added to uniquely identify each record.

### Second Normal Form (2NF)

Partial dependencies were removed by separating the information into independent entities. Separate tables were created for suppliers, products, warehouses, purchases, and inventory movements, reducing data duplication.

### Third Normal Form (3NF)

Transitive dependencies were eliminated by creating independent tables for cities and categories. The supplier, product, and warehouse tables were then linked using foreign keys (**CityID** and **CategoryID**), preventing redundant data storage and improving data integrity.

---

## 4. Final Normalized Result

After completing the normalization process, the database was organized into several related tables connected through primary and foreign keys.

The final tables are:

* CITY
* CATEGORY
* SUPPLIER
* PRODUCT
* WAREHOUSE
* PURCHASE
* MOVEMENT

This new structure eliminates data redundancy, improves data consistency, simplifies database maintenance, and allows SQL queries to be performed more efficiently. Furthermore, the resulting database complies with the First, Second, and Third Normal Forms (1NF, 2NF, and 3NF), ensuring a well-organized and reliable relational database.
