# Database Systems Cheat Sheet

A comprehensive reference for Database Design, SQL, and Performance Optimization.

---

## 🎨 1. ER & EER Modeling
Quick guide to diagram symbols and rules:
* **Entities**: Rectangles represent Strong Entities; Double Rectangles represent Weak Entities.
* **Relationships**: Diamonds represent standard relationships; Double Diamonds are Identifying.
* **Attributes**: Ovals for standard; Double Ovals for Multivalued; Dashed Ovals for Derived.
* **Participation**: Double line for Total (mandatory); Single line for Partial.
* **ISA Rule**: Use only if a subclass "IS A" member of the superclass (e.g., Laptop IS A Computer).



---

## 📐 2. Relational Algebra & SQL
A breakdown of how data is queried and processed.



### SQL Execution Order
1. `FROM` → 2. `WHERE` → 3. `GROUP BY` → 4. `HAVING` → 5. `SELECT` → 6. `ORDER BY` → 7. `LIMIT`.

### Relational Operations
* **Selection ($\sigma$)**: Filters rows based on a condition.
* **Projection ($\pi$)**: Filters specific columns and removes duplicates.
* **Natural Join ($\bowtie$)**: Combines tables based on common attributes.
* **Division ($\div$)**: Finds tuples that match ALL values in another set.

---

## 📏 3. Normalization (Data Integrity)
Rules to reduce redundancy and prevent update anomalies:
* **1NF**: Ensure atomic values; no multivalued or composite attributes.
* **2NF**: Must be in 1NF with no partial dependencies (non-keys must depend on the whole key).
* **3NF**: Must be in 2NF with no transitive dependencies (non-keys cannot depend on other non-keys).

---

## ⚡ 4. Transactions & Concurrency
* **ACID**: Atomicity (all or nothing), Consistency, Isolation, and Durability.
* **2-Phase Locking (2PL)**: Includes a Growing Phase (acquiring locks) and a Shrinking Phase (releasing).
* **Concurrency Issues**: Dirty Reads, Lost Updates, Unrepeatable Reads, and Phantom Reads.

---

## 📁 5. Physical Storage & Performance
| File Type | Search (Key) | Search (Non-Key) | Insert |
| :--- | :--- | :--- | :--- |
| **Heap** | $O(b/2)$ | $O(b/2)$ | $O(1)$ |
| **Ordered** | $O(log_2 b)$ | $O(b)$ | $O(b)$ |
| **Hash** | $O(1)$ | N/A | $O(1)$ |

* **B+ Trees**: Balanced search trees where data is stored only in leaf nodes for efficiency. 
* **Indexing**: Primary Index (on ordering key), Clustering Index (non-key), and Secondary Index (dense).



---

## 🛡️ 6. Security & Implementation
* **Access Control**: Discretionary (DAC) and Mandatory (MAC) models.
* **Bell-LaPadula**: "No Read Up" (higher clearance) and "No Write Down" (lower clearance).
* **PHP Pattern**: Standard `mysqli` pattern for connecting, querying, and fetching results.
