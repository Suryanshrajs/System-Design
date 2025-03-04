## **🏦 Consistency in Distributed Systems**

Consistency in distributed systems refers to the principle that all clients should see the same view of the data at the same time. Here's an explanation of consistency, its types, and factors influencing it.

### **🧐 Understanding Consistency**

Imagine you have ₹100 in your bank account. You try to withdraw ₹100, but the ATM says your balance is zero. This discrepancy occurs because the bank's database isn't consistent.

> Consistency: When a client requests data from a system, the data should always be consistent, ensuring all clients receive the same, up-to-date information.
> 

Consider a scenario with movie tickets. There are four seats available. A person in Delhi checks and sees four seats. Simultaneously, someone in Pune checks and sees the same. If the Delhi person books a ticket, the Pune system should immediately reflect the change. If updates aren't synchronized across different databases, the system becomes inconsistent.

When a client requests data from a system, the data should always be consistent, ensuring all clients receive the same, up-to-date information.

### **⚖️ Monolithic vs. Distributed Systems**

| **Feature** | **Monolithic System** | **Distributed System** |
| --- | --- | --- |
| Structure | Everything is in the same system | Components are spread across multiple servers/locations |
| Network Calls | Fewer network calls | More network calls |
| Horizontal Scaling | Not easily horizontally scalable | Horizontally scalable |
| Extra Steps | No need for extra steps for consistency | Requires extra steps to ensure consistency across all servers |
| Update Time | Updates are immediate | Updates take time to propagate across all servers |
| Consistency | Inherently more consistent | Requires effort to maintain consistency |

In a monolithic system, everything is within the same system, leading to fewer network calls. In contrast, a distributed system involves components spread across multiple servers, leading to more network calls.

Let's say an update takes time $T_1$ on one server and $T_2$ on another. The entire system remains inactive for a time of $max(T_1, T_2)$ until all servers are updated.

### **🚀 Factors Improving Consistency**

To improve consistency in a distributed system:

- **Increase Network Speed**: Faster networks facilitate quicker data synchronization.
- **Stop Read Operations**: Prevent read operations until all servers are updated.
- **Application Proximity**: Keep servers close to users to reduce latency.

In short:

> Increase network speed, reduce distance, and halt read operations until all replicated data is updated.
> 

### **🛡️ Strong vs. Eventual Consistency**

| **Feature** | **Strong Consistency** | **Eventual Consistency** | **Weak Consistency** |
| --- | --- | --- | --- |
| Read Requests | User read requests are halted | Allows read operations to be done | Not all nodes need to be updated |
| Data | Always reads the right data | Eventually becomes consistent; some users might receive old data temporarily | It is not necessary that all Notes should be updated |
| Use Cases | Critical applications like train ticket booking | Social media posts | Situations where immediate consistency isn't crucial for business logic |
- **Strong Consistency**: User read requests are halted until all replicas are updated. This ensures that the user always reads the correct, up-to-date data.
- **Eventual Consistency**: Allows read operations to proceed. Some users might temporarily receive old data, but eventually, all data becomes consistent.
- **Weak Consistency:** Not all nodes need to be updated.

The choice of consistency model depends on the specific application. For instance, train ticket booking requires strong consistency, while social media posts can tolerate eventual consistency.
