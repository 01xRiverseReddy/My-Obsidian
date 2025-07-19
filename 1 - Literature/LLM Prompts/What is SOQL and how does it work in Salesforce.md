**SOQL** (Salesforce Object Query Language) is Salesforce's proprietary query language used to **retrieve records** from Salesforce objects (both standard and custom), similar to SQL but tailored for the Salesforce data model.

---

### **What is SOQL?**

- It’s used to **query a single object (or related objects)**.
- You use SOQL when you **know the object** you're querying and want to filter data with conditions.
- It works in Apex code, Developer Console, Workbench, API calls, and more.

---

### **Basic Syntax:**

```apex
SELECT Name, Email FROM Contact WHERE LastName = 'Smith'
```

This query fetches `Name` and `Email` fields from the `Contact` object where `LastName` equals `'Smith'`.

---

### **How SOQL Works in Salesforce:**

1. **Compiles to Salesforce's Query Plan**:
   - SOQL queries are optimized and translated into a query plan based on indexing, filters, and limits.

2. **Respects Security**:
   - Automatically enforces **Object and Field-Level Security (FLS)** and **Sharing Rules** (unless you use `WITH SECURITY_ENFORCED` or system mode).

3. **Supports Relationships**:
   - You can traverse parent-child relationships (both directions):

   **Child to Parent (dot notation):**
   ```apex
   SELECT Name, Account.Name FROM Contact
   ```

   **Parent to Child (subquery):**
   ```apex
   SELECT Name, (SELECT LastName FROM Contacts) FROM Account
   ```

4. **Returns a List of sObjects**:
   ```apex
   List<Contact> contacts = [SELECT Name FROM Contact WHERE LastName = 'Smith'];
   ```

---

### **Key Features of SOQL:**

- **Filtering** with `WHERE`, `AND`, `OR`, `IN`, `LIKE`, `LIMIT`, etc.
- **Aggregation**: `COUNT()`, `AVG()`, `SUM()`, `MAX()`, `MIN()` (though limited).
- **Ordering**: `ORDER BY Name ASC`
- **Pagination**: Use `OFFSET` and `LIMIT`.
- **Date functions**: e.g., `WHERE CreatedDate = LAST_N_DAYS:30`
- **FOR clauses**: `FOR UPDATE`, `FOR VIEW`, `FOR REFERENCE`

---

### **Example Use Cases:**

- Retrieve all open opportunities for a specific account.
- Get top 5 contacts by last modified date.
- Fetch related object data (e.g., all contacts for accounts in a region).

---

### **SOQL vs SQL – Key Differences:**

| Feature                  | SOQL                               | SQL                          |
|--------------------------|-------------------------------------|-------------------------------|
| Joins                    | Through object relationships        | Explicit JOIN statements      |
| Modifications (INSERT/UPDATE) | Not supported (SOQL is read-only) | Supported                     |
| DML Operations           | Performed separately in Apex        | Part of SQL                   |
| Object Model             | Salesforce object-relational model  | Traditional relational model  |

---

### **Best Practices for SOQL:**

1. **Avoid SELECT *** — Always specify required fields.
2. **Use indexed fields** in `WHERE` for better performance.
3. **Bulkify your code** — Don’t run SOQL in loops.
4. **Limit the number of records** using `LIMIT`.
5. **Use relationship queries** instead of multiple queries when possible.
6. **Leverage tools like Query Plan** to analyze query performance.

---

Let me know if you want help with optimizing a SOQL query or writing one for a specific use case.