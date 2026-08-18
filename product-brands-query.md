# 🚀 SQL Core Concept: Inner Join Mastery

Welcome to my SQL practice repository! In this project, I demonstrate how to efficiently combine data from multiple tables using the `INNER JOIN` clause.

## 📝 Problem Statement
We have two separate tables in a retail production database:
1. `production.products` (Contains product details but only has a brand ID reference).
2. `production.brands` (Contains the actual names of the brands).

**Goal:** Fetch a clean list showing each **Product Name** right next to its corresponding **Brand Name**.

---

## 💻 SQL Query

```sql
SELECT 
    p.product_name AS Product,  
    b.brand_name AS Brand
FROM 
    production.products p 
INNER JOIN 
    production.brands b ON p.brand_id = b.brand_id;
```

---

## 🔍 Code Breakdown

- **`SELECT p.product_name AS Product...`**: Selects the raw product name and renames the column header to "Product" for clean reporting.
- **`FROM production.products p`**: Sets the primary table and gives it a short alias (`p`) to keep the code clean.
- **`INNER JOIN production.brands b`**: Joins the secondary brands table (aliased as `b`). It ensures we *only* get rows where a match exists in both tables.
- **`ON p.brand_id = b.brand_id`**: The matching condition. It links the Foreign Key (`brand_id` in products) to the Primary Key (`brand_id` in brands).

---

## 📊 Expected Output Example

| Product | Brand |
| :--- | :--- |
| Trek 820 - 2026 | Trek |
| Ritchey Timberwolf Frameset | Ritchey |
| Surly Wednesday Frameset | Surly |
| Electra Cruiser 1 - 2026 | Electra |

---

## 💡 Key Takeaway
Using explicit table aliases (`p` and `b`) is a best practice in production environments. It prevents column ambiguity errors and makes complex multi-join queries significantly easier to read and maintain.

---
⭐ *Feel free to star this repository if you found this SQL breakdown helpful!*
