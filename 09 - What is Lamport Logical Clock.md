## **⏰ Time in Distributed Systems**

In distributed systems, **time** is used to determine the **sequence of events**, i.e., which event occurred before another.

Consider three servers located in Australia, the US, and India. Due to their different locations, they will have different times. This discrepancy makes it difficult to determine the order of events in a distributed system, unlike a monolithic system where everything happens at the same time.

The significance of time is to establish the sequence of events. Physical clocks are inadequate for this purpose due to the different times across locations in a distributed system. To overcome the disadvantages of physical clocks, we use **Lamport Clocks**.

### **Lamport Logical Clocks 🕰️**

Lamport Logical Clocks are used to determine the sequence of events.

> The significance of time is solely to determine the sequence of events.
> 

Each process has a counter. The counter is incremented as events occur. When a process receives a message, it updates its counter based on the maximum of its own counter and the sender's counter plus one.

### **How Lamport Clocks Work ⚙️**

Consider two processes, P1 and P2. Each process has a counter.

1. **Event Occurrence**: When an event occurs, increment the counter by one.
2. **Message Reception**: When a process receives a message, it updates its counter to the maximum of its current counter and the received counter plus one.
    
    counter=max(counterown,counterreceived)+1counter=max(counterown,counterreceived)+1
    

### **Example 💡**

Let's walk through an example:

- Initially, both processes have a counter of 0.
- As events occur in each process, the counter is incremented.
- When a process sends a message, it includes its counter value.
- When a process receives a message, it updates its counter by taking the max of the local counter and the received counter + 1.

## **Practical Demonstration**

The following steps and diagram illustrates the use of Lamport Logical Clocks.

1. **Initialization**:
    - Each process begins with a counter set to zero.
    - Processes, such as P1 and P2, operate independently, each managing their own event sequence.
2. **Event Increments**:
    - Whenever an event occurs within a process, its counter is incremented by one.
    - This increment reflects the progression of events locally within that process.
3. **Message Handling**:
    - Upon receiving a message, a process compares its current counter value with the timestamp included in the received message.
    - The process updates its counter to be the maximum of its current value and the received timestamp plus one, ensuring synchronization that respects the happened-before relationship.
4. **Counter Updates**:
    - When a message is sent, no immediate counter update occurs on the sender side related to the send action itself. The counter is updated upon the occurrence of local events or when receiving messages from other processes.

The numbers associated with each event indicate the order in which the events occurred.
