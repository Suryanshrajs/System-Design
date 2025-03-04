## **⚖️ Load Balancing**

### **Load Balancing Definition**

> Load balancing is the process of efficiently distributing network traffic across all nodes in a distributed system. It determines which node a particular request should be sent to, ensuring that the load is distributed evenly.
> 

### **Example Scenario**

Imagine a company that has four servers and needs to deploy changes to them.

1. A **JAR** file is created.
2. The **JAR** file is deployed to all four servers.
3. A **virtual IP (VIP)**, such as **`xyz.com`**, is used to access the servers. This **VIP** is not tied to a specific node.
4. When a user enters **`xyz.com`** in their browser, the request is directed to the **load balancer**.
5. The **load balancer** has code that determines which node the request should be sent to, based on the **IP addresses** of the nodes.

### **🎯 Roles of Load Balancers**

- **Load Distribution:** Ensures an equal distribution of load over every node, preventing some nodes from being idle while others are overloaded.
- **Health Checks:** Monitors the health of each node. If a node fails a health check, the **load balancer** stops sending requests to it.
- **High Availability:** Ensures high availability, throughput, and scalability. The **load balancer** redirects requests to healthy nodes if one fails.

### **✅ When to Use Load Balancing**

| **Scenario** | **Use Load Balancing?** | **Scaling Type** |
| --- | --- | --- |
| Monolithic Application | No | Vertical |
| Microservices | Yes | Horizontal |
- **Monolithic applications:** Typically do not require load balancing because they are vertically scaled (i.e., a single machine is upgraded).
- **Microservices/Distributed Systems:** Utilize load balancing to horizontally scale applications across multiple machines.

### **⚠️ Challenges of Load Balancing**

- **Single Point of Failure:** The **load balancer** itself can become a single point of failure.
- **Solution:** Implement a **passive load balancer** as a backup in case the primary **load balancer** fails.

### **💡 Advantages of Using Load Balancers**

- **Handles High Traffic:** Distributes incoming traffic efficiently across multiple servers.
- **Better User Experience:** High availability ensures a better user experience with minimal downtime.
- **Prevents Downtime:** Redirects traffic from failed servers to healthy ones.
- **Flexibility:** Easily add or remove servers as needed.
- **Scalability:** Facilitates horizontal scaling by distributing load across new servers.
- **Redundancy:** Ensures that the system remains operational even if some servers fail.

### **⚙️ Load Balancing Algorithms**

### **Round Robin**

The **load balancer** distributes requests to servers in a rotational fashion.

1. First request goes to the first server.
2. Second request goes to the second server.
3. Third request goes to the third server.
4. Fourth request goes to the fourth server.
5. Fifth request goes back to the first server, and so on.

### **Weighted Round Robin**

If a server has more capacity (e.g., 3x), the **load balancer** sends more requests to it. For example, if one server can handle three requests for every one request handled by other servers, the **load balancer** will distribute requests accordingly.

### **IP Hash Algorithm**

The **load balancer** uses a hash function to determine which server to send a request to based on the client's IP address.

## **⚖️ Load Balancing Algorithms**

### **Source IP Hash**

- **Source IP hash** involves applying a hash function to the source IP address to determine which node should handle a request.
- The benefit of this approach is that requests from a specific client are always directed to the same node. This is beneficial when persistence of information is needed.
- Algorithm:
    1. Get Source IP
    2. Apply Hash Function
    3. The hash will point to a specific node to send the request to

### **Source IP's**

- **Source IP's** combine the client's source IP address with the destination IP address to create a key. This key is then used to determine which node should handle the request.
- It ensures that requests from a particular client are consistently routed to the same node, useful when maintaining session affinity is crucial.
- Algorithm:
    1. Combine the client's source IP with the destination IP address
    2. The combined key is used to determine which node handles the request

### **Least Connection Algorithm**

- The **least connection algorithm** directs incoming requests to the node with the fewest active connections.
- This method aims to distribute the load evenly across all nodes, minimizing response time by ensuring no single node is overwhelmed with requests.
- Algorithm:
    1. A request comes in, and the load balancer determines which node to send the request to, in order to minimize response time.
    2. The algorithm checks which node has the least active connections.
    3. The request is sent to the node with the least active connections.

### **Static vs Dynamic Load Balancing**

- **Static** load balancing algorithms have predefined rules for directing requests to servers, such as in Round Robin or IP Hash. These rules do not change during runtime.
- **Dynamic** algorithms, like Least Connections, make decisions based on real-time conditions, such as the current number of active connections on each node.
- The following table depicts the differences between the static and dynamic algorithms discussed:
    
    
    | **Algorithm** | **Type** | **Description** |
    | --- | --- | --- |
    | Round Robin | Static | Requests are distributed sequentially to each server. |
    | IP Hash | Static | A hash function is applied to the IP address to determine which server to send the request to. |
    | Source IP's | Static | Combines the client's source IP address with the destination IP address to create a key to determine which node should handle the request. |
    | Least Connections | Dynamic | Directs traffic to the server with the fewest active connections. |
