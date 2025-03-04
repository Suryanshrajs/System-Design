## **📦 Caching**

### **🤔 What is Caching?**

Imagine clicking on an Instagram profile to view their bio, profile picture, posts, followers, and following. Until there's a change (new post, bio update, follower change), the profile remains static.

> Caching is a technique used to store and retrieve data quickly. Instead of fetching data from the database every time, data is retrieved from a "cache," which is faster.
> 

When you click on a profile multiple times, fetching data from the database each time takes time. All the different components of the profile are retrieved separately from the database, one by one.

Caching allows us to retrieve this data from memory. The first time you view a profile, the data comes from the database. Then, a **caching layer** is added. Subsequent views retrieve the data from this layer, which is faster due to the use of primary memory (RAM). This reduces API calls and network usage, speeding up the process.

Well-established applications like Instagram, WhatsApp, Facebook, Flipkart, and Amazon use caching to reduce loading times.

### **Caching Example: Gaana App**

When working on the Gaana app, specifically on the Gaana Plus profile, a user's profile includes:

- Transaction history
- Cute balance
- Gaana Plus subscription details (validity)

Without caching, each of these components would be fetched from separate APIs, leading to delays when loading the profile.

Caching allows the data to load from the database once and stores it in a caching layer. Subsequent requests retrieve the data directly from the caching layer. The duration for which the data is cached can be defined or manually deleted when a user takes a new subscription.

### **🗓️ When to Use Caching**

Caching is used for:

- Storing **HTML assets**
- Storing **API responses**
- Storing **database queries**

Consider Netflix plans, which rarely change. Instead of fetching the plans from the database every time, they can be retrieved from the cache, avoiding unnecessary code execution.

### **Netflix Plans Example**

Consider the Netflix function **`getPlans()`** which fetches all the available plans. Without caching, the process would be:

1. Call the database.
2. Receive a response.
3. Format the data.
4. Return the data.

With caching, the process is reduced. If the data is available in the cache, it is returned directly, avoiding the database call and formatting steps.

When plans are updated, the **`setPlans()`** function deletes the cache, ensuring that the next request fetches the latest data from the database and updates the cache.

### **⚡️ Why Caching is Fast**

Caching is fast because:

- The application does not have to run any code.
- No API calls are made.
- No network calls occur.
- Data is stored in RAM, which is faster than accessing a disk or database.

### **🗄️ Types of Caching**

There are two main types of caching:

- **In-Memory/Local Cache:** Data is stored locally on a server.
- **Distributed/External Cache:** Data is shared across multiple servers or nodes.

### **In-Memory Cache**

When data is stored locally on a server, it is called an in-memory cache.

### **Distributed Cache**

In a distributed system with multiple servers handling requests, a distributed cache is necessary. All nodes share the cache.

Examples include:

- Memcached
- Redis

### **Choosing a Caching Type**

| **Feature** | **In-Memory Cache** | **Distributed Cache** |
| --- | --- | --- |
| Storage Location | Local server | Shared across multiple servers |
| Use Case | Single-server applications | Distributed systems |
| Examples | N/A | Memcached, Redis |

### **💡 When to Use Caching**

Caching is best used when:

- The application is **read-intensive.**
- There is **static content.**

### **Read-Intensive Applications**

Caching is beneficial for read-intensive applications like Twitter, Wikipedia, and Times of India.

For example, a Times of India article can be viewed by millions of users. Caching prevents the system from accessing the database for each view, reducing load and improving response times.

### **Static Content**

Caching is also useful for static content such as HTML and images.

### **🌐 Application Server Cache vs. CDN**

- **Application Server Cache:** Caches database queries, API responses, and function responses.
- **CDN (Content Delivery Network):** A type of caching that serves static content from geographically located servers.

CDNs reduce the time it takes to load content by serving it from a server closer to the user. For example, static content on Amazon is served from CDNs.
