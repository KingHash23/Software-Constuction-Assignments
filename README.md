# Software Construction Assignment

**Topic:** Microservices Architecture in Modern Software Systems

##**Name:** OBBA MARK CALVIN     S23B23\047      B24277
##**Course:** BSCS 3:2
##**Course Unit:** Software Construction

---

# 1. How Microservices are Used at Netflix

Netflix is one of the most famous examples of a company successfully using a **microservices architecture**. Instead of building its system as a single large application (monolithic architecture), Netflix built its platform using **hundreds of smaller independent services** that work together to deliver the full streaming experience.

A monolithic system means all features of an application run inside one large codebase and are deployed together. This makes updates slower and increases the risk that a failure in one component can bring down the entire system. To overcome these limitations, Netflix migrated to microservices around **2009–2012** when it moved its infrastructure to the cloud.

In a microservices architecture, each service is responsible for a **single business capability** and communicates with other services using **lightweight APIs**, usually REST APIs. This allows each service to be built, deployed, and scaled independently.

Today Netflix runs **thousands of microservices** that support different parts of the platform including streaming, recommendations, billing, and user management.

---

## Key Ways Netflix Uses Microservices

### 1. Independent Services for Different Functions

Netflix divides its platform into many services such as:

* User account management
* Video streaming service
* Recommendation engine
* Billing and subscription management
* Content search service
* Playback service
* Device management service

Each of these services performs a **specific function** within the Netflix ecosystem.

For example:

* The **recommendation service** analyzes viewing patterns and suggests movies or shows a user may like.
* The **streaming service** manages the delivery of video content to users' devices.
* The **billing service** handles subscription payments and account plans.

These services communicate with each other using **APIs and service discovery systems**.

Because each service is independent, Netflix engineers can update or improve one service without modifying the others.

---

### 2. Independent Development and Deployment

Another major advantage Netflix gained from microservices is **team autonomy**.

Different engineering teams are responsible for different microservices. Each team can:

* Develop features independently
* Deploy updates without affecting other services
* Fix bugs without stopping the entire platform

Netflix uses **Continuous Integration and Continuous Deployment (CI/CD)** systems which allow engineers to push updates frequently.

Because services are deployed independently, Netflix can release **hundreds of updates every day** without interrupting the streaming service.

---

### 3. Massive Scalability

Netflix serves **hundreds of millions of users globally**, meaning the system must handle huge traffic loads.

Microservices allow Netflix to scale **specific services instead of scaling the entire system**.

Examples:

* During peak viewing hours, the **video streaming service** can scale up by adding more servers.
* When users browse movies, the **search service** can scale independently.
* The **recommendation system** may require additional computing power to process viewing data.

This approach allows Netflix to allocate computing resources **only where they are needed**, reducing waste and improving efficiency.

---

### 4. Fault Isolation and System Resilience

Microservices also improve **system resilience** because failures can be isolated.

In a monolithic architecture, if one component fails, the entire application may crash. However, in microservices architecture:

* A failure in one service does not necessarily stop other services.

Example:

* If the **recommendation system fails**, users can still watch movies.

Netflix also developed a famous testing tool called **Chaos Monkey**, which randomly shuts down services in production to test whether the system can recover from failures.

This ensures the platform remains **highly reliable and fault tolerant**.

---

### 5. Cloud-Based Infrastructure

Netflix runs most of its infrastructure on **Amazon Web Services (AWS)**.

Cloud infrastructure allows Netflix to:

* Automatically scale services
* Distribute services across multiple data centers
* Maintain high availability globally

Netflix also uses several technologies such as:

* Load balancing
* Service discovery
* Content Delivery Networks (CDNs)
* Containerization

These technologies help deliver video content quickly and reliably to users around the world.


---

# 2. Two Other Companies That Use Microservices

Many major technology companies use microservices architecture to build **large and scalable platforms**.

---

## 1. Amazon

Amazon was one of the earliest adopters of microservices architecture.

### How Amazon Uses Microservices

Amazon divides its e-commerce platform into thousands of small services responsible for different tasks, including:

* Product catalog management
* Payment processing
* Order management
* Shipping and logistics
* Customer reviews
* Recommendation systems

Each service communicates with others through APIs.

### Benefits Amazon Achieved

Using microservices allowed Amazon to:

* Enable multiple development teams to work independently
* Release features faster
* Scale different parts of the platform during high demand
* Handle massive traffic during events like **Black Friday**

---

## 2. Uber

Uber also uses microservices to power its global ride-sharing platform.

### How Uber Uses Microservices

Uber divides its system into services responsible for:

* Ride requests
* Driver matching
* Payments
* Trip tracking
* Notifications

Each service communicates through internal APIs.

### Benefits Uber Achieved

Microservices allowed Uber to:

* Scale rapidly as the company expanded internationally
* Improve reliability of ride matching
* Deploy updates without disrupting the entire system
* Manage large amounts of real-time location data

---

# 3. Companies That Moved Away from Microservices

Although microservices offer many benefits, they can also introduce **complexity and higher operational costs**. Some companies later moved back to **monolithic architectures**.

---

## 1. Segment

Segment, a customer data infrastructure company, initially used microservices but later moved parts of its platform back to a monolithic system.

### Reasons for the Change

* High operational complexity
* Difficult debugging across multiple services
* Increased infrastructure costs

### Result

By consolidating services into a monolith, Segment simplified system management and improved performance.

---

## 2. Amazon Prime Video

Amazon Prime Video also redesigned part of its architecture from microservices to a monolithic system.

### Reasons for the Change

Engineers discovered the system had:

* Very high cloud infrastructure costs
* Excessive communication between services
* Increased latency

### Outcome

After redesigning the system:

* Infrastructure costs were reduced by **over 90%**
* System performance improved
* Operations became simpler

---

# Microservices vs Monolithic Architecture

| Feature         | Microservices Architecture       | Monolithic Architecture         |
| --------------- | -------------------------------- | ------------------------------- |
| Structure       | Many small independent services  | One large application           |
| Development     | Teams work independently         | Developers work on one codebase |
| Deployment      | Services deployed independently  | Entire system deployed together |
| Scalability     | Individual services scale        | Entire application scales       |
| Fault Isolation | Failure affects only one service | Failure may crash the system    |
| Complexity      | More complex to manage           | Simpler for smaller systems     |

---

# Example of a Simple Microservices Architecture

```
                +-------------------+
                |     User App      |
                | (Web / Mobile)    |
                +---------+---------+
                          |
                    API Gateway
                          |
     -------------------------------------------------
     |           |            |            |          |
+-----------+ +-----------+ +-----------+ +-----------+
|  Account  | | Streaming | | Billing   | | Search    |
| Service   | | Service   | | Service   | | Service   |
+-----------+ +-----------+ +-----------+ +-----------+
      |             |             |            |
      -----------------------------------------
                          |
                   +-------------+
                   |   Database  |
                   +-------------+
```

### Explanation

1. **User Applications** access the system through web or mobile apps.
2. **API Gateway** routes requests to the appropriate service.
3. **Microservices** handle different functions such as streaming, billing, and search.
4. **Databases** store system data used by services.

---

# Conclusion

Microservices architecture has transformed how modern software systems are designed and built. Companies such as **Netflix, Amazon, and Uber** use microservices to build scalable systems capable of supporting millions of users worldwide.

However, microservices also introduce complexity and higher operational costs. Some companies such as **Segment and Amazon Prime Video** have moved back to monolithic architectures to simplify development and reduce infrastructure costs.

Therefore, choosing between microservices and monolithic architecture depends on the **size, complexity, and requirements of the system being developed**.

---

# References

* Netflix Technology Blog
* AWS Architecture Case Studies
* Uber Engineering Blog
* Software Architecture: The Hard Parts (Ford, Richards)
