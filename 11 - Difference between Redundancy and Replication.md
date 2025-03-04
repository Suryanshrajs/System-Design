## **🛡️ Redundancy vs. Replication**

### **Redundancy**

- **Redundancy** is simply the **duplication of nodes**, ensuring that if one node or component fails, a duplicate is available to serve customers.
    
    > Redundancy means having multiple servers with the same code. If one server fails, the others can take over.
    > 

### **Types of Redundancy**

1. **Active Redundancy**:
    - Every unit is active and can accept requests.
    - All servers are on and in working condition.
    - Requests are distributed among all active servers via a **load balancer**.
2. **Passive Redundancy**:
    - Only one server is active and handles requests.
    - Other servers are in an inactive state.
    - If the active server fails, an inactive server is activated to take over.

### **🔄 Replication**

- **Replication** is **redundancy plus synchronization**. It involves duplicating data across multiple servers and ensuring that the data is consistent across all servers.
    
    > Replication is copying data to multiple servers and keeping it synchronized.
    > 
- Typically used in the context of databases.
    - For example, if there are 3 databases, one might contain numbers "1, 2, 3".
    - Replication would copy the numbers to the other 2 databases to be identical to the first.
    - If another number "4" is added to the first database, the other two databases would need to synchronize this change for all the databases to remain identical.

### **Types of Replication**

1. **Active Replication**:
    - All nodes are active and can accept read and write requests.
    - All nodes are synchronized, ensuring data consistency.
2. **Passive Replication**:
    - Involves a **master-slave** setup.
    - The master node is responsible for all read and write operations.
    - Slave nodes are synchronized with the master node.
    - If the master node fails, one of the slave nodes becomes the new master.
        - **Synchronous**: changes made to the master are immediately propagated to the slaves.
        - **Asynchronous**: changes are queued and updated later on.

### **⚖️ Redundancy vs. Replication**

| **Feature** | **Redundancy** | **Replication** |
| --- | --- | --- |
| Definition | Duplication of nodes | Redundancy + Synchronization |
| Data Consistency | Not necessarily synchronized | Data is synchronized across all nodes |
| Use Case | General server duplication | Typically used for databases |

### **Load Balancer**

- The **load balancer** decides which node a client's request should be sent to.
