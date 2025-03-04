## **💾 Cache Eviction Strategies**

This video discusses strategies for **cache eviction**, which is the process of deleting data from a cache after a certain time. This is necessary because caches have a limited size.

### **Why Evict Cache?**

- **Limited Size**: Caches have limited space, so unnecessary data needs to be removed.
- **Configuration Changes**: If configurations (like Netflix plans) change, outdated cached data needs to be deleted. For instance, caching four plans for 10 years becomes problematic if a fifth plan is added.
- **TTL (Time To Live)**: Instead of setting very long TTLs (e.g., 10 years), shorter durations like 4 hours are used. After this time, data is automatically deleted from the cache.

### **Cache Misses**

- When a request comes in and the data isn't in the cache, it's called a **cache miss**.
- The system then retrieves data from the database.
- Subsequently, this data is stored in the cache so that future requests can be served directly from the cache, avoiding the need to hit the database.

### **🔄 Eviction Strategies**

Here are several cache eviction strategies:

### **LRU (Least Recently Used)**

- Deletes data that hasn't been used in a long time.
- Requires additional memory to track the usage of each cached item.

### **MRU (Most Recently Used)**

- Deletes the most recently used data.
- Useful in specific business logic scenarios.

### **LFU (Least Frequently Used)**

- Deletes data based on how frequently it's used.
- Example: If a "Bollywood" category on Netflix is rarely accessed, its cached data is removed.

### **FIFO (First In, First Out)**

- Deletes the oldest data first.
- If the cache is full, the first item that was added is the first to be removed.
    
    For instance, consider a cache that can store only four data items. If five items are added, the first item is deleted to make room for the fifth.
    

### **LIFO (Last In, First Out)**

- Deletes the most recently added data first.

### **Random Replacement**

- Randomly evicts cache items without considering usage frequency or age.
- Each item has an equal probability of being evicted.
