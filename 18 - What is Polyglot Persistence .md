## **📚 Polyglot Persistence**

This lecture discusses **polyglot persistence**, which involves using multiple types of databases within a single application to meet diverse requirements.

> Polyglot persistence refers to the practice of using different database technologies to handle different data storage needs within a single application. This approach acknowledges that no single database is optimal for all situations.
> 

### **Types of Databases**

There are several types of databases, including:

- **RDBMS** (Relational Database Management System)
- **Key-Value Database**
- **Columnar Database**
- **Graph Database**
- **Document Database**

### **⚙️ Examples of Database Systems**

Here are some examples of database systems that fall under each type:

- **PostGres**: RDBMS
- **Redis**: Key-Value Database
- **MongoDB**: Document Database
- **Cassandra**: Columnar Database

### **🛒 E-commerce Platform Example**

Consider an e-commerce platform. Different parts of the application can benefit from different database types:

| **Data** | **Database Type** | **Rationale** |
| --- | --- | --- |
| Cart Data | Key-Value Database | Simple data structure suitable for quick storage and retrieval. |
| Completed Orders | Document Database | Handles nested, complex data structures with evolving details. |
| Inventory & Prices | RDBMS | High consistency is needed, especially for payment-related information. |
| Customer Social Graph | Graph Database | Efficiently manages relationships between customers. |

### **🤔 Application Scenario**

If an application uses different kinds of databases to fulfill its requirements, it is an example of **polyglot persistence**.
