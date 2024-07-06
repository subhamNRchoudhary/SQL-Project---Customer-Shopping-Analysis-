SQL-Project---Customer-Shopping-Analysis



### Project Overview

In this SQL project, we aim to analyze customer shopping data from a fictional retail store. The dataset includes information such as customer demographics, purchase details, payment methods, and shopping locations. Our goal is to perform various SQL operations to gain insights into customer behavior, product preferences, and transaction patterns.

### Dataset Example

```sql
INSERT INTO Invoices (customer_id, gender, age, category, quantity, price, payment_method, invoice_date, shopping_mall)
VALUES
('C241288', 'Female', 28, 'Clothing', 5, 1500.4, 'Credit Card', '2022-05-08', 'Kanyon'),
('C111565', 'Male', 21, 'Shoes', 3, 1800.51, 'Debit Card', '2021-12-12', 'Forum Istanbul'),
('C266599', 'Male', 20, 'Clothing', 1, 300.08, 'Cash', '2021-09-11', 'Metrocity'),
('C169650', 'Female', 66, 'Clothing', 2, 600.16, 'Credit Card', '2022-09-08', 'Istinye Park'),
('C337046', 'Female', 53, 'Books', 4, 60.6, 'Cash', '2021-10-24', 'Kanyon'),
('C227836', 'Female', 28, 'Clothing', 5, 1500.4, 'Credit Card', '2022-05-24', 'Forum Istanbul'),
('C121056', 'Female', 49, 'Cosmetics', 1, 40.66, 'Cash', '2022-03-13', 'Istinye Park'),
('C293112', 'Female', 32, 'Clothing', 2, 600.16, 'Credit Card', '2021-01-13', 'Mall of Istanbul'),
('C293455', 'Male', 69, 'Clothing', 3, 900.24, 'Credit Card', '2021-11-04', 'Metrocity');
```

### SQL Operations

#### 1. Create a Table with Unique ID Numbers

```sql
CREATE TABLE Invoices (
 id INT PRIMARY KEY AUTO_INCREMENT,
 customer_id VARCHAR(20),
 gender VARCHAR(10),
 age INT,
 category VARCHAR(50),
 quantity INT,
 price DECIMAL(10,2),
 payment_method VARCHAR(20),
 invoice_date DATE,
 shopping_mall VARCHAR(50)
);
```

#### 2. Insert Data into the Table

```sql
-- Insert your data here using the example provided above
```

#### 3. Select Records

```sql
SELECT * FROM Invoices;
```

#### 4. Filter Records Based on Certain Conditions

```sql
SELECT * FROM Invoices WHERE category = 'Clothing';
SELECT * FROM Invoices WHERE category = 'Food & Beverage';
```

#### 5. Aggregate Functions

```sql
SELECT AVG(price) AS avg_price, MAX(price) AS max_price, MIN(price) AS min_price FROM Invoices;
SELECT AVG(price) AS avg_price FROM Invoices;
SELECT MIN(price) AS min_price FROM Invoices;
SELECT MAX(price) AS max_price FROM Invoices;
```

#### 6. Group By

```sql
SELECT category, COUNT(*) AS total_count FROM Invoices GROUP BY category;
SELECT gender, COUNT(*) AS total_count FROM Invoices GROUP BY gender;
```

#### 7. Subqueries

```sql
SELECT * FROM Invoices WHERE price < (SELECT AVG(price) FROM Invoices);
```

#### 8. Update Records

```sql
UPDATE Invoices SET price = price * 1.1 WHERE category = 'Shoes';
```

#### 9. Sorting

```sql
SELECT * FROM Invoices ORDER BY price DESC;
SELECT * FROM Invoices ORDER BY price ASC;
```

#### 10. Limit

```sql
SELECT * FROM Invoices LIMIT 3;
```

#### 11. Case Statements

```sql
SELECT category, CASE
 WHEN price > 1000 THEN 'Expensive'
 ELSE 'Affordable'
 END AS price_category FROM Invoices;
```

#### 12. Views

```sql
CREATE VIEW Expensive_Invoices AS
SELECT * FROM Invoices WHERE price > 2000;
```

### Conclusion

This SQL project provides a comprehensive overview of customer shopping analysis techniques. By leveraging SQL queries, we uncovered valuable insights into the dataset, including average purchase prices, popular product categories, and customer demographics. The project demonstrates the power of SQL in extracting meaningful information from data, which can drive informed business decisions and enhance overall performance. Whether you're a data analyst, business manager, or aspiring SQL practitioner, this project serves as a practical guide to leveraging SQL for retail analytics.


