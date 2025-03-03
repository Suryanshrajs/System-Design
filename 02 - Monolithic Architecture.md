## **🏛️ Monolithic Architecture**

Before diving into monolithic architecture, it's essential to understand what **architecture** means in the context of application development.

> Architecture refers to the internal design details for building an application, outlining how the application is structured and how its components interact.
> 

The most straightforward architecture when starting an application is the **monolithic architecture**.

A typical web application comprises three parts:

- **Frontend**
- **Backend**
- **Data storage**

Monolithic architecture consolidates these three components into a single deployable unit.

> Monolithic Architecture means that the entire frontend, backend, and data storage are written and deployed together in a single unit.
> 

If all functionalities reside in a single place, it's indicative of a monolithic application.

Benefits of monolithic architecture:

- Simplicity
- Reduced network latency
- Enhanced security
- Easier integration testing

When you're just starting, you can use different architectures, but the monolithic system could be the simplest to begin with. Since everything is located together, there are minimal network calls. Compared to distributed systems with components on different servers, monolithic architecture centralizes code, improving security through unified management and simplifying integration testing. Developers unfamiliar with diverse architectures find it more approachable.

## **🚫 Disadvantages of Monolithic Architecture**

Drawbacks include:

- A single point of failure affecting the entire application.
- The need to redeploy the entire system for even minor updates.
- Challenges in changing the programming language for a single module due to potential incompatibilities.

## **🆚 Monolithic vs. Distributed Systems**

| **Feature** | **Monolithic Architecture** | **Distributed Systems** |
| --- | --- | --- |
| Deployment | Single deployable unit | Multiple independent services |
| Network Latency | Lower due to internal communication | Higher due to inter-service network calls |
| Security | Centralized, easier to manage | Complex, requires securing individual services |
| Testing | Easier integration testing | More complex, requires testing interactions between services |
| Codebase | Unified, all components in one place | Distributed, code scattered across multiple services |
| Module Updates | Requires redeployment of the entire application | Allows independent deployment of individual services |
| Language Changes | Difficult due to potential incompatibilities | Easier, as each service can use different languages |
| Starting | Simpler for starting applications | More complex to set up |

## **🌐 Website vs. Web Application**

- **Website**: Read-only content.
- **Web Application**: Interactive with read and write capabilities (e.g., Snapchat).
