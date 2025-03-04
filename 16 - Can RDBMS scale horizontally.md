## **💾 RDBMS: Relational Database Management System**

In this video, we will study RDBMS, or Relational Database Management System. In the last video, we looked at file-based storage systems and their disadvantages, such as slow speed, redundancy, and poor security. RDBMS overcomes these issues.

### **🤔 What is RDBMS?**

When someone asks you what RDBMS is, you can say:

> It is a software that performs operations on a relational database.
> 

These operations include:

- Storing
- Retrieving
- Deleting
- Updating

Data is stored in **tables**, and the tables inside the database are **related** to each other with the help of **foreign keys**.

### **✅ Advantages of RDBMS**

The disadvantages of the file-based storage system are the advantages of RDBMS:

- **No data redundancy and inconsistency**: Redundancy is reduced. You can apply constraints in the table so that if one row comes, another row will not come.
- **Data searching**: Built-in searching capability. In RDBMS, you can search data with the help of queries, which are built-in.
- **Data concurrency**: RDBMS has a locking system. Until one transaction is complete, the second transaction will not occur.
- **Data integrity**: You can apply some constraints on a column to ensure that only numbers are entered in that column.

### **❌ Disadvantages of RDBMS**

- **Rigid schema**: No flexibility. Every table has a particular structure that must be followed.
- **High cost**
- **Scalability issues**: RDBMS is not easily scalable.

### **Vertical vs. Horizontal Scalability**

**Vertical Scaling**: Adding more resources to a single machine.

**Horizontal Scaling (Sharding)**: Adding more machines to the system and distributing the data across them. For example, if you have 1 TB of data, you can use ten 100 GB systems and distribute the data across them.

Horizontal scaling is difficult in RDBMS.

### **Horizontal Scaling Example**

Consider Amazon's customers and their orders. Assume there are only two tables: Customer and Order. There are 100 million entries in the Order table, totaling 10 TB of data. The goal is to distribute this across ten systems, each storing 1 TB of data.

The Order table is divided across different systems. Each row in the Order table has a mapping to the Customer table. Therefore, the Customer table also needs to be partitioned.

If a customer has orders on machine A and machine B, and their entry in the Customer table needs to be accessed, it becomes problematic. This is the issue with horizontal scaling in RDBMS.

### **📝 Summary of RDBMS Disadvantages**

| **Disadvantage** | **Description** |
| --- | --- |
| Rigid Schema | Lack of flexibility; requires adherence to a specific table structure. |
| High Cost | RDBMS solutions can be expensive to implement and maintain. |
| Scalability Issues | Difficulties in scaling, particularly with horizontal scaling due to the need to partition related tables, causing complexities. |
