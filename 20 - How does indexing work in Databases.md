## **🗂️ Indexing in Databases**

Before diving into indexing, let's understand why it's important with a real-world analogy:

Imagine your house is completely disorganized. If you need to find your car keys, it will take a lot of time because you don't know where anything is. This is similar to a database table that isn't organized. Searching for specific data can be very time-consuming.

Now, think of a medical store. When you ask for a specific medicine, the storekeeper can quickly locate it because everything is well-organized. This is analogous to **indexing** in databases.

### **🔍 Why Indexing?**

Consider an **unordered array**. If you want to find a specific number, you have to use **linear search**, checking each element one by one.

For example, if you have an array of 1 million elements and the number you're looking for is at the end, you have to check all 1 million elements. This takes a lot of time, specifically, it takes O(n)O(n) time, where nn is the number of elements.

If the array were **sorted**, you could use **binary search**, which has a time complexity of O(log n)O(log n), which is much faster. Indexing helps us bring that same speed boost to database queries.

### **📚 Indexing Defined**

> Indexing is a way to implement binary search in our tables.
> 

### **🧮 Indexing Example**

Let's say we have a table named **Students** with columns like **Name** and **Net Worth**.

If you run a query like:

```sql
SELECT Name FROM Students WHERE NetWorth = 4000;

```

Without indexing, the database would have to check every row in the table to find the student with a net worth of 4000. If there are 10 million students and the student you're looking for is at the end, it would take a long time.

To optimize this, we can create an index on the **NetWorth** column.

### **💾 How Indexing Works**

Indexing involves allocating a separate memory location for the column you're indexing, like **NetWorth**. In this separate memory location, the **NetWorth** column is stored in a sorted manner. Along with each **NetWorth** value, there is a **pointer** to the actual row in the original table.

For example, if the NetWorth values are 10000, 20000, 300, and 4000, the index would sort them as 300, 4000, 10000, and 20000. Each of these values would have a pointer to the corresponding row in the **Students** table.

Here's how the separate memory location looks after indexing:

| **NetWorth** | **Pointer to Row** |
| --- | --- |
| 300 | Row 3 |
| 4000 | Row 4 |
| 10000 | Row 1 |
| 20000 | Row 2 |

Now, when you run the query with the **`WHERE`** clause, the database will use the index to quickly find the matching **NetWorth** value in O(log n)O(log n) time, and then use the pointer to retrieve the corresponding row.

> Indexing creates a lookup table with the column and pointer to the memory location of the row containing this column.
> 

### **🤔 Interview Perspective**

A common interview question is how to optimize a table with millions of rows. The answer is to use indexing on the appropriate columns.

Follow-up questions may include:

- **What happens with indexing?**
    - A separate memory location is created with the column stored in a sorted manner, along with pointers to the original rows.
- **What data structure is used for this separate memory location?**
    - B-trees are commonly used for indexing.

### **⚠️ When to Use Indexing**

Indexing isn't always the right solution. You should use indexing in **read-intensive databases**, where read queries are much more frequent than write queries.

If your table has a lot of **write queries** (i.e., **`INSERT`**, **`UPDATE`**), indexing can slow things down. Each **`INSERT`** operation requires an entry in the table and an entry in the separate memory location (index), which also needs to be sorted.

Situations where you should avoid indexing:

- Small databases
- Write-intensive databases
