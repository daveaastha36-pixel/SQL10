1.
Create two tables: AppOrders (for orders placed via a food delivery app like Zomato) and InStoreOrders (for direct restaurant orders), each with columns: order_id, customer_name, amount, and order_date. Insert at least 3 sample records into each table.

***SOLUTION***

-- Create AppOrders table
CREATE TABLE AppOrders (
    order_id INT PRIMARY KEY,
    customer_name VARCHAR(50),
    amount DECIMAL(10,2),
    order_date DATE
);

-- Create InStoreOrders table
CREATE TABLE InStoreOrders (
    order_id INT PRIMARY KEY,
    customer_name VARCHAR(50),
    amount DECIMAL(10,2),
    order_date DATE
);

-- Insert sample records into AppOrders
INSERT INTO AppOrders VALUES
(101, 'Amit', 350.00, '2025-06-01'),
(102, 'Priya', 420.00, '2025-06-02'),
(103, 'Rahul', 280.00, '2025-06-03');

-- Insert sample records into InStoreOrders
INSERT INTO InStoreOrders VALUES
(201, 'Neha', 500.00, '2025-06-01'),
(202, 'Priya', 300.00, '2025-06-04'),
(203, 'Karan', 450.00, '2025-06-05');



2.
Write a SQL query using UNION to combine all unique customer names from both AppOrders and InStoreOrders tables into a single list.

***SOLUTION***
SELECT customer_name
FROM AppOrders

UNION

SELECT customer_name
FROM InStoreOrders;



3.
Write a SQL query using UNION ALL to display every order (including duplicates if any) from both AppOrders and InStoreOrders, showing order_id, customer_name, amount, and order_date.

***SOLUTION***

SELECT order_id, customer_name, amount, order_date
FROM AppOrders

UNION ALL

SELECT order_id, customer_name, amount, order_date
FROM InStoreOrders;



4.
Demonstrate the difference between UNION and UNION ALL by adding a duplicate customer_name in both tables, then running both queries and noting the difference in the result count.<br><br><em><strong>Hint:</strong> UNION removes duplicates, UNION ALL does not.</em>

***SOLUTION***
INSERT INTO AppOrders VALUES
(104, 'Neha', 375.00, '2025-06-06');

