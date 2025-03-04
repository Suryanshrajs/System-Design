## **💾 RDBMS vs NoSQL**

In the last video, we learned about RDBMS, which is essentially a system for storing data in **tables**. These tables contain rows and columns of data. However, RDBMS has some challenges, such as **slow speed** and difficulty in **scaling**. Specifically, RDBMS does not scale horizontally very well. While horizontal scaling is possible, it can be complex to implement.

To overcome these limitations, **NoSQL** databases were developed.

> NoSQL stands for "Non-SQL" or "Non-Relational" databases.
> 

NoSQL is an **umbrella term** that encompasses four types of databases:

- Key-value
- Document
- Columnar
- Graph

## **🔑 Key-Value Databases**

**Key-value databases** store data in the form of keys and their corresponding values. This type of database is commonly used for **caching**. An example of a key-value database is Redis.

## **📄 Document Databases**

**Document databases** combine the best aspects of both RDBMS and NoSQL databases.

> Document databases combine the relationship concepts from relational databases with the dynamic schemas and horizontal scaling capabilities of NoSQL databases.
> 

MongoDB is a popular document database. Unlike traditional databases, document databases do not have a fixed **schema**. This allows for more flexibility in adding new documents and columns without requiring schema changes.

## **📊 Columnar Databases**

In **columnar databases**, columns are stored together instead of rows.

> Columnar databases are optimized for data analysis because they allow for rapid aggregation of data.
> 

In a regular, row-based database, data is grouped by rows. However, in a columnar database, data is grouped by **columns**. When querying a subset of data in a specific column, the database only needs to read that specific column, which speeds up the process.

For example, if we have a table with columns for employee name, employee ID, city, and salary, and we want to find the maximum salary, a row-based database would need to read through all the rows. In contrast, a columnar database only needs to read the salary column, making the query much faster.

Columnar databases are commonly used for machine learning and data analysis. An example of a columnar database is **Snowflake**.

## **🕸️ Graph Databases**

**Graph databases** represent and store entities and their relationships in the form of a graph data structure.

> Graph databases are commonly used for social networking websites.
> 

Graph databases are useful when data is in the form of a graph, such as in social networks.

For example, on LinkedIn, connections are organized by degree:

- First-degree connections are those directly connected to you.
- Second-degree connections are those connected to your first-degree connections.
- Third-degree connections are those connected to your second-degree connections.

This forms a network or graph of connections.

Another example is Google Maps, where every place is connected to others. This allows Google Maps to provide directions. An example of a graph database is **Neo4j**.

## **🧰 Choosing the Right Database**

Here's a summary of when to use each type of database:

| **Database Type** | **Use Case** | **Example** |
| --- | --- | --- |
| Key-Value | Caching, simple data storage (e.g., shopping cart, scorecards) | Redis |
| Document | Flexible schema requirements | MongoDB |
| Columnar | Machine learning, data analysis, aggregations | Snowflake |
| Graph | Social networking, relationship-based data (e.g., LinkedIn connections, Google Maps) | Neo4j |

## **💳 Payments and RDBMS**

For payments, which require high consistency, it's best to use an RDBMS like **Oracle** or **MySQL** instead of NoSQL.
