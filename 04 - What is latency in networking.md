## **🌐 Latency in Web Applications**

Latency in web applications refers to the time it takes for a request to travel from the user to the server and back.

If a user enters **`facebook.com`** in their browser:

1. The request goes to Facebook's server.
2. The server processes the request and sends a response back to the user.
3. The time taken for this entire round trip is the **latency.**

Latency can be represented as:

Δt=t1+t2+t3

Where:

- t1 is the time taken for the request to reach the server.
- t2 is the time taken for the response to reach back to the user.
- t3 is the computation time on the server.

> Latency = Network Delay + Computation Delay

### **Monolithic vs. Distributed Architectures**

When comparing **monolithic** and **distributed** architectures, latency considerations differ:

- **Monolithic Architecture**: All components are deployed together, minimizing network delays.
- **Distributed Architecture**: Components are deployed separately, increasing latency due to network calls between different modules.

In a distributed setup, the initial and final network costs are always present. However, monolithic architectures avoid network calls within the application because the entire codebase is deployed together, resulting in process-to-process calls.

## **📉 Reducing Latency**

High latency leads to a poor user experience. Here are some ways to reduce latency in web applications:

### **📦 Caching**

Caching involves adding a layer that stores frequently accessed data closer to the user, reducing the time it takes to retrieve that data. Instead of fetching the data from the server every time, the system checks the cache first.

### **🌍 Content Delivery Networks (CDNs)**

CDNs are networks of geographically distributed servers that store static data.

For example, if a user in India needs to access static data from a server in the US, it would take longer due to geographical distance. To mitigate this, a CDN server located closer to the user in India can store a copy of the data and serve it to the user, reducing latency.

### **Caching vs. CDN**

While both caching and CDNs aim to reduce latency, they operate differently:

- **Caching**: Stores information for a set period of time on a computer (usually on the server-side).
- **CDN**: Uses geographically distributed servers to store static content closer to users.

**Caching Example:**

Consider a function that performs a thousand lines of code and returns a value based on a user ID. If the same user ID is used repeatedly, the function will return the same value.

In such cases, caching can be implemented to store the result of the function for a specific user ID. The next time the same user ID is used, the cached result can be returned immediately without executing the thousand lines of code again.

**Key Differences:**

| **Feature** | **Caching** | **CDN** |
| --- | --- | --- |
| Location | Typically on the same server where the application is deployed. | Geographically distributed servers. |
| Data Type | Dynamic data, results of computations, etc. | Static content such as images, videos, stylesheets, and JavaScript. |
| Proximity to User | Closer to the server (may still involve network latency for the user) | Closer to the user (minimizes network latency). |

### **⚙️ Hardware Improvements**

Upgrading the hardware of the server can also reduce latency by improving processing and response times.

## **🤔 Distributed Systems and Latency**

Distributed systems often have higher latency than monolithic systems due to the increased network calls between distributed components. However, the benefits of distributed systems, such as scalability and fault tolerance, often outweigh the increased latency. By using techniques such as caching and CDNs, it is possible to reduce latency in distributed systems and improve the overall user experience.
