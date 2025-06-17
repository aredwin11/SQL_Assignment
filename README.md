# SQL Assignment

This repository contains five sets of structured SQL questions solved using a single database named `ecommerce`. The tasks include table creation, data insertion, and a variety of SQL queries focused on aggregation, transformation, filtering, and window functions.


---

## Task 1: Ecommerce Database

### Tables Involved:

| Table Name             | Description                          |
|------------------------|--------------------------------------|
| `users`                | Stores user information              |
| `gold_member_users`    | Subset of users with gold membership |
| `sales`                | Records of product purchases         |
| `product`              | Product catalog                      |

### Actions Performed:

- Created and populated all four tables with appropriate data types.
- Displayed metadata: listed all table names and contents.
- Counted records in all tables using a single query with `UNION ALL`.
- Calculated total amount spent by each user.
- Extracted distinct dates each customer visited the site.
- Found first product purchased by each user using `ROW_NUMBER()`.
- Identified most purchased item per user along with purchase count.
- Retrieved users who are not listed as gold members.
- Calculated total spending while user was a gold member.
- Filtered and displayed users whose names start with the letter 'M'.
- Retrieved distinct user IDs.
- Renamed the column `price` to `price_value` in the `product` table.
- Updated `product_name` from `"Ipad"` to `"Iphone"`.
- Renamed `gold_member_users` table to `gold_membership_users`.
- Added a new column `Status` to indicate gold membership (`Yes`/`No`).
- Performed `DELETE` and `ROLLBACK` operations on user records.
- Inserted a duplicate product record and detected duplicates using `GROUP BY` and `HAVING`.

---

## Task 2: Product Details Summary

### Table:

| Table Name        | Description                      |
|-------------------|----------------------------------|
| `product_details` | Stores daily sold product names  |

### Actions Performed:

- Created and inserted product sales data by date.
- Queried number of different products sold per date.
- Used `STRING_AGG` (or `GROUP_CONCAT`) to list products sold per date in a single row.

### Sample Output:

| sell_date   | num_sold | product_list                     |
|-------------|----------|----------------------------------|
| 2020-05-30  | 3        | Basketball, Headphones, T-Shirt  |
| 2020-06-01  | 2        | Book, Pencil                     |
| 2020-06-02  | 1        | Mask                             |

---

## Task 3: Department Salary Aggregation

### Table:

| Table Name   | Description                              |
|--------------|------------------------------------------|
| `dept_tbl`   | Employee salary data with department info|

### Actions Performed:

- Created and populated department-wise employee salary records.
- Extracted department names using string parsing (`RIGHT`, `CHARINDEX`, `SUBSTRING`).
- Aggregated total salary for each department using `GROUP BY`.

### Sample Output:

| dept_name | total_salary |
|-----------|--------------|
| BIO       | 12300        |
| CHEM      | 37000        |
| MATH      | 30000        |
| SCIENCE   | 20000        |

---

## Task 4: Email Signup Analytics

### Table:

| Table Name     | Description                             |
|----------------|-----------------------------------------|
| `email_signup` | Stores user email IDs and signup dates  |

### Actions Performed:

- Created and inserted mixed email domain data with some `NULL` values.
- Filtered Gmail accounts using `LIKE '%@gmail.com'`.
- Retrieved latest and earliest Gmail signup dates.
- Calculated difference between dates in days.
- Replaced `NULL` values with `'1970-01-01'` using `COALESCE()`.

### Sample Output:

| count_gmail_account | latest_signup_date | first_signup_date | diff_in_days |
|---------------------|--------------------|-------------------|--------------|
| 2                   | 2022-02-01         | 2020-09-08        | 511          |

---

## Task 5: Sales Data Analysis Using Window Functions

### Table:

| Table Name   | Description                         |
|--------------|-------------------------------------|
| `sales_data` | Daily quantity sold per product     |

### Actions Performed:

- Created and inserted product-wise daily sales records.
- Used `RANK()` to identify the most recent sales per product.
- Compared daily quantity sold using `LAG()` window function.
- Retrieved the first and last quantity sold per product using `FIRST_VALUE()` and `LAST_VALUE()`.

---



