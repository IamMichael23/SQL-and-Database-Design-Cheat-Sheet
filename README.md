# Western CS3319: Databases I Cheat Sheet

A comprehensive study guide and reference for Western University's **CS3319: Databases I**. This repository covers everything from conceptual design to physical storage and security implementation.

---

## 🎨 1. ER & EER Modeling
Rules for conceptual database design:

* **Entities**: Rectangles represent Strong Entities; Double Rectangles represent Weak Entities.
* **Relationships**: Diamonds for standard relationships; Double Diamonds for Identifying Relationships.
* **Attributes**: Ovals for standard; Double Ovals for Multivalued; Dashed Ovals for Derived.
* **Participation**: Double line indicates Total Participation (mandatory); Single line for Partial.
* **ISA Rule**: Only use if the subclass "IS A" member of the superclass (e.g., Laptop IS A Computer).
* **Specialization/Generalization**: Specialization is Top-down (Employee → Secretary); Generalization is Bottom-up (Car → Vehicle).

---

## 📐 2. Relational Algebra & SQL


### Relational Algebra
* **Selection ($\sigma_{cond}$)**: Filters rows satisfying a condition.
* **Projection ($\pi_{attrs}$)**: Selects specific columns and removes duplicates.
* **Natural Join ($\bowtie$)**: Joins on common attributes and removes duplicate columns.
* **Division ($\div$)**: Template for "Find X who did ALL Y" queries.

### SQL Execution Order
1. `FROM` → 2. `WHERE` → 3. `GROUP BY` → 4. `HAVING` → 5. `SELECT` → 6. `ORDER BY` → 7. `LIMIT`.

---

## 📏 3. Normalization (Data Integrity)
* **1NF**: All attributes must contain atomic (indivisible) values.
* **2NF**: Must be in 1NF with no partial dependencies (non-prime attributes must depend on the entire primary key).
* **3NF**: Must be in 2NF with no transitive dependencies (non-prime attributes cannot depend on other non-prime attributes).

---

## ⚡ 4. Transactions & Concurrency
* **ACID Properties**: Atomicity, Consistency, Isolation, and Durability.
* **2-Phase Locking (2PL)**: Consists of a Growing Phase (acquiring locks) and a Shrinking Phase (releasing locks).
* **Concurrency Problems**: Includes Lost Updates, Dirty Reads, Unrepeatable Reads, and Phantom Reads.
* **Deadlock**: Occurs when two or more transactions wait eternally for each other's resources.

---

## 📁 5. Physical Storage & Performance
| File Type | Search (Key) | Search (Non-Key) | Insertion |
| :--- | :--- | :--- | :--- |
| **Heap** | $O(b/2)$ | $O(b/2)$ | $O(1)$ |
| **Ordered** | $O(log_2 b)$ | $O(b)$ | $O(b)$ |
| **Hash** | $O(1)$ | N/A | $O(1)$ |

* **B+ Trees**: Balanced search trees where data is stored only in leaf nodes.
* **Indexing**: Primary Index (on ordering key), Clustering Index (non-key ordering field), and Secondary Index (dense/any field).



---

## 🛡️ 6. Security & PHP Implementation
* **Bell-LaPadula**: "No read up" (higher classification) and "No write down" (lower classification).
* **SQL Security**: Use `GRANT` to provide privileges and `REVOKE` to remove them.
* **PHP Pattern**: Standard `mysqli_connect` pattern for server-side database interaction.

---

⭐ **If you found this study guide helpful for CS3319, feel free to leave a star!**
