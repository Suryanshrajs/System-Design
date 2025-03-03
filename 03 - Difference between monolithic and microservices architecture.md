## **💻 Distrubuted Systems vs Monolithic Systems**

### **🧱 Monolithic Systems**

In a monolithic system, all modules of an application reside within a single codebase and are deployed together.

### **🌐 Distributed Systems**

Distributed systems differ significantly from monolithic systems. Here's a comparison:

| **Feature** | **Monolithic Systems** | **Distributed Systems** |
| --- | --- | --- |
| Modules | In a single codebase | Modules are separate. |
| Deployment | Deployed together in one place | Executed independently in different places. |
| Data | Centralized | Data can be separated. |
| Failure Points | **Single point of failure**: If it goes down, the whole system fails. | Impact is isolated; failure of one part doesn't necessarily affect the entire system. |
| Definition | N/A | > A collection of multiple individual systems connected through a network, which allows for resource sharing and modular independence. |

### **⚙️ Achieving Fault Tolerance in Distributed Systems**

Monolithic systems have a **single point of failure** because if one component fails, the entire system can go down. Distributed systems offer better resilience.

Consider a scenario where a task is distributed across five machines. If one machine fails, the remaining four continue operating.

### **💾 Addressing Data Loss**

When a machine fails in a distributed system, data loss is a significant concern. **Replication** addresses this issue.

> Replication: Creating copies of data across multiple machines.
> 

For example, if data exists on machine A, a copy is made on machine B. If machine A fails, the data is still accessible from machine B. The number of replicas can vary (two, three, or more machines).

### **✅ Advantages of Distributed Systems**

- **Scalability**: Horizontally scalable, meaning you can add more machines to increase capacity. Distribute tasks across multiple machines to improve performance.
- **No Single Point of Failure**: If one machine fails, others continue to operate.
- **Fault Tolerance**: The system can withstand failures without complete disruption.

### **❌ Disadvantages of Distributed Systems**

- **Complexity**: Managing numerous nodes requires additional administrative overhead, including monitoring network traffic and balancing loads.
- **Security Challenges**: Securing multiple nodes increases complexity. Each node must be secured individually, requiring more time and resources.
