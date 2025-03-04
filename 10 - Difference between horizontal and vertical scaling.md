## **🚀 Scalability**

### **What is Scalability?**

> Scalability is the ability of a system to maintain or improve its performance and response time as the number of requests increases. A scalable system remains efficient rather than becoming overloaded or unresponsive.
> 

### **Vertical vs. Horizontal Scaling**

The primary difference between vertical and horizontal scaling lies in how resources are added to handle increased load.

### **⬆️ Vertical Scaling (Scaling Up)**

Vertical scaling involves increasing the **resources** of a single server or machine.

- **Definition**: Upgrading the **hardware** of an existing server (e.g., increasing RAM, upgrading the processor, adding more storage).
- **Example**:
    - Initially, a server handles 100 users.
    - After a month, the user base grows to 100,000.
    - To accommodate this growth, the server's RAM and hard disk are upgraded.

### **➡️ Horizontal Scaling (Scaling Out)**

Horizontal scaling involves adding **more machines** to a system.

- **Definition**: Distributing the load across multiple servers or machines (e.g., adding more servers to a database cluster).
- **Example**:
    - A database is 100GB in size.
    - Instead of using one large server, the data is distributed across four servers, each holding 25GB.
    - If more space is needed (e.g., 125GB total), another server with 25GB is added.

### **Pros and Cons**

### **⚖️ Vertical Scaling**

| **Pros** | **Cons** |
| --- | --- |
| Easy implementation | Single point of failure |
| Less power consumption | Limited scalability |
| Easier to manage | Resources must be high quality, costly |

### **⚖️ Horizontal Scaling**

| **Pros** | **Cons** |
| --- | --- |
| No single point of failure | Management complexity increases |
| Uses cheaper resources | Higher power consumption |
| Can scale using commodity/lower-end hardware | Security concerns increase with more resources |

## **🔑 Key Takeaways**

- **Vertical Scaling**:
    - Involves upgrading the hardware of a **single server**.
    - Suitable for applications where scaling requirements are **limited**.
- **Horizontal Scaling**:
    - Involves adding **more servers** to distribute the load.
    - Ideal for applications that require **high availability** and can benefit from distributed resources.
- With horizontal scaling, work is distributed among different servers. For example, instead of storing a 1TB database on one server, it's spread across multiple servers.
- With vertical scaling, if a laptop has a 1TB hard disk and needs an additional 250GB, the extra storage is added to the same laptop.
