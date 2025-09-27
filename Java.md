# Java Backend Interview Questions & Answers

This document provides a complete set of **Java Backend Interview Questions & Answers** structured from beginner to advanced, with practical system design concepts.

---

## 🟢 Beginner Level (Core Java)

### 1. What are the main features of Java?
**Answer (Interview style):**  
Java is platform-independent because of the JVM, it’s object-oriented, secure, and robust. It also supports multithreading, automatic garbage collection, and has a rich standard library. These features make Java widely used in backend development.

---

### 2. Difference between JDK, JRE, and JVM?
**Answer:**  
- JDK is the Java Development Kit, it provides tools for developing and compiling Java programs.  
- JRE is the Java Runtime Environment, which is needed to run Java applications.  
- JVM is the Java Virtual Machine, it executes the bytecode.  

So, JDK = JRE + Development tools, and JRE = JVM + libraries.

---

### 3. What is the difference between `==` and `.equals()`?
**Answer:**  
`==` compares references, whether two objects point to the same memory location.  
`.equals()` is used to compare the actual content.  
For example, two `String` objects with the same value may not be `==`, but `.equals()` will return true.

---

### 4. What is a constructor in Java?
**Answer:**  
A constructor is a special method used to initialize objects. It has the same name as the class and doesn’t have a return type. It’s automatically called when an object is created.

---

### 5. Difference between checked and unchecked exceptions?
**Answer:**  
Checked exceptions are checked at compile time, like `IOException`.  
Unchecked exceptions occur at runtime, like `NullPointerException`.  
In backend development, we usually handle checked exceptions explicitly with try-catch or throws.

---

## 🟡 Intermediate Level (OOP, Collections, Multithreading)

### 6. Can you explain the four pillars of OOP?
**Answer:**  
- **Encapsulation** → Binding data and methods together, usually through classes.  
- **Abstraction** → Exposing only necessary details, like using interfaces and abstract classes.  
- **Inheritance** → Reusing code by deriving classes from parent classes.  
- **Polymorphism** → Same method behaving differently, like method overloading and overriding.

---

### 7. What is the difference between `ArrayList` and `LinkedList`?
**Answer:**  
- `ArrayList` is backed by an array, so accessing elements is faster (O(1)), but inserting in the middle is slower.  
- `LinkedList` is backed by nodes, so insertions and deletions are faster (O(1)) if you already have the reference, but access is slower (O(n)).  

---

### 8. What is the difference between `HashMap` and `ConcurrentHashMap`?
**Answer:**  
`HashMap` is not thread-safe, multiple threads can cause data inconsistency.  
`ConcurrentHashMap` is thread-safe, it uses segment-level locking or buckets to allow concurrent reads and controlled writes, making it better for multi-threaded backend applications.

---

### 9. What is the difference between `synchronized` and `volatile`?
**Answer:**  
- `synchronized` is used to lock a block or method so that only one thread can access it at a time.  
- `volatile` ensures visibility of changes to variables across threads, but doesn’t guarantee atomicity.  

So, `synchronized` is for both visibility and atomicity, `volatile` is only for visibility.

---

### 10. How does Java handle memory management?
**Answer:**  
Java uses automatic garbage collection. Objects are stored in heap memory, and unused objects are collected by the garbage collector. The JVM uses different generations (young, old, permanent/metaspace) to optimize collection.

---

## 🔴 Advanced Level (Spring, Hibernate, Concurrency, Performance)

### 11. What is Dependency Injection in Spring?
**Answer:**  
Dependency Injection is a design pattern where objects don’t create their dependencies themselves. Instead, they are injected by the Spring container. This makes code loosely coupled and easier to test.

---

### 12. What is the difference between Spring Boot and Spring MVC?
**Answer:**  
Spring MVC provides a framework for building web applications, but you have to configure a lot manually.  
Spring Boot makes development faster by providing auto-configuration, embedded servers (like Tomcat), and production-ready features with minimal setup.

---

### 13. What is the difference between Hibernate and JDBC?
**Answer:**  
- JDBC is a low-level API for interacting with databases using SQL queries.  
- Hibernate is an ORM framework that maps Java objects to database tables, so we work with objects instead of SQL directly.  
Hibernate handles caching, lazy loading, and transactions better than raw JDBC.

---

### 14. How do you handle transactions in Spring?
**Answer:**  
We use the `@Transactional` annotation to manage transactions declaratively. Spring takes care of starting, committing, or rolling back transactions automatically. This avoids boilerplate transaction code and makes business logic cleaner.

---

### 15. Explain microservices in backend development.
**Answer:**  
Microservices is an architecture where applications are broken down into small, independent services that communicate through APIs (usually REST or gRPC). Each service can be deployed, scaled, and maintained independently.  
For example, in an e-commerce app, we may have separate services for inventory, payments, and orders.

---

## 🟣 System Design & Practical Backend

### 16. How would you design a scalable backend for a high-traffic application?
**Answer:**  
I would use a microservices architecture with load balancers in front. Each service would use caching (like Redis), a database with read replicas, and messaging queues (like Kafka or RabbitMQ) for asynchronous tasks.  
I’d also add monitoring tools like Prometheus + Grafana and implement CI/CD for smooth deployments.

---

### 17. What’s the difference between REST and GraphQL?
**Answer:**  
REST exposes fixed endpoints with fixed responses, while GraphQL allows clients to query exactly the data they need.  
GraphQL reduces over-fetching but is more complex to implement. REST is simpler and widely used in backend APIs.

---

### 18. How do you handle security in Java backend applications?
**Answer:**  
I follow best practices like:  
- Using Spring Security for authentication and authorization.  
- Storing passwords with hashing algorithms like bcrypt.  
- Securing APIs with JWT or OAuth2.  
- Validating inputs to prevent SQL injection and XSS.  
- Using HTTPS and secure headers.

---

### 19. Explain caching strategies in backend systems.
**Answer:**  
We can use:  
- **In-memory caching** with tools like Redis or Ehcache.  
- **Write-through** cache (write goes to cache + DB).  
- **Write-behind** cache (write goes to cache, async update DB).  
- **Read-through** cache (fetches from DB if not in cache).  

Caching improves performance and reduces DB load.

---

### 20. What are some performance tuning techniques in Java?
**Answer:**  
- Use connection pooling with databases.  
- Use caching to reduce redundant calls.  
- Optimize garbage collection with proper JVM tuning.  
- Minimize synchronization in multithreaded apps.  
- Profile and monitor using tools like JVisualVM or JProfiler.

---

## 🟠 Extended Advanced Questions (21 - 50)

### 21. What are Java Streams and why are they useful?
**Answer:**  
Streams allow functional-style processing of collections. They make operations like filtering, mapping, and reducing more concise and parallelizable. For example, `list.stream().filter(x -> x > 10).collect(Collectors.toList());`.

---

### 22. Difference between parallelStream() and stream()?
**Answer:**  
`stream()` is sequential.  
`parallelStream()` divides tasks into multiple threads for parallel execution.  
Parallel streams improve performance but may cause issues if tasks are not thread-safe.

---

### 23. What is immutability in Java and why is it important?
**Answer:**  
Immutable objects cannot be modified after creation. For example, `String` is immutable. Immutability is important for thread safety and caching, as state cannot be changed unexpectedly.

---

### 24. What are Java Records?
**Answer:**  
Records (introduced in Java 14) are a concise way to define immutable data classes. Instead of writing boilerplate getters, equals, and hashCode, records generate them automatically.

---

### 25. Explain Functional Interfaces in Java.
**Answer:**  
A functional interface has exactly one abstract method. Examples: `Runnable`, `Callable`, `Comparator`.  
They are used with lambda expressions and method references.

---

### 26. What are default and static methods in interfaces?
**Answer:**  
- **Default methods** allow interfaces to provide implementations.  
- **Static methods** belong to the interface itself.  
This reduces the need for abstract classes and makes API evolution easier.

---

### 27. Explain the difference between Thread and Runnable.
**Answer:**  
`Thread` is a class, `Runnable` is an interface.  
We usually implement `Runnable` because it allows flexibility and avoids multiple inheritance issues.

---

### 28. What is ThreadPoolExecutor?
**Answer:**  
ThreadPoolExecutor manages a pool of worker threads. Instead of creating new threads for every task, tasks are submitted to a queue, improving performance in concurrent applications.

---

### 29. What is the difference between Callable and Runnable?
**Answer:**  
- `Runnable` doesn’t return a result or throw checked exceptions.  
- `Callable` returns a result and can throw exceptions.  

---

### 30. Explain CompletableFuture in Java.
**Answer:**  
`CompletableFuture` represents an asynchronous computation. It allows chaining with `.thenApply()`, `.thenAccept()`, and combining tasks with `.thenCombine()`.

---

### 31. What is the difference between Monolith and Microservices architecture?
**Answer:**  
- Monolith: One large application, harder to scale and deploy.  
- Microservices: Small independent services, easier to scale, but more complex infrastructure.

---

### 32. What is API Gateway in microservices?
**Answer:**  
API Gateway acts as a single entry point for clients, handling authentication, routing, load balancing, and rate limiting.

---

### 33. How do you handle inter-service communication in microservices?
**Answer:**  
- **Synchronous**: REST or gRPC.  
- **Asynchronous**: Messaging queues like Kafka or RabbitMQ.  

---

### 34. Explain eventual consistency.
**Answer:**  
In distributed systems, eventual consistency means that while data may not be consistent at all times, it will become consistent eventually. Used in systems like Cassandra or DynamoDB.

---

### 35. How do you scale databases in backend systems?
**Answer:**  
- Vertical scaling (bigger servers).  
- Horizontal scaling (sharding, replication).  
- Using caching layers (Redis, Memcached).  

---

### 36. What is CAP theorem?
**Answer:**  
CAP theorem states that in distributed systems, you can only guarantee two of the three:  
- **Consistency**  
- **Availability**  
- **Partition tolerance**

---

### 37. Explain ACID properties.
**Answer:**  
- **Atomicity**: All or nothing transactions.  
- **Consistency**: Transactions bring DB from one valid state to another.  
- **Isolation**: Concurrent transactions don’t affect each other.  
- **Durability**: Once committed, data is permanent.

---

### 38. Explain BASE properties in NoSQL.
**Answer:**  
- **Basically Available**  
- **Soft state**  
- **Eventual consistency**  

Used in distributed NoSQL systems.

---

### 39. What is Lazy Loading in Hibernate?
**Answer:**  
Lazy loading defers object initialization until it’s needed. Improves performance by avoiding unnecessary DB calls.

---

### 40. Explain the difference between Eager and Lazy fetching.
**Answer:**  
- **Eager**: Fetches associated objects immediately.  
- **Lazy**: Fetches associated objects only when needed.  

---

### 41. What are Hibernate Caching levels?
**Answer:**  
- **First level cache**: Session-scoped.  
- **Second level cache**: SessionFactory-scoped, supports Ehcache, Redis.  
- **Query cache**: Stores results of queries.

---

### 42. How does Spring Security handle authentication?
**Answer:**  
It uses filters, authentication providers, and user details service. Authentication can be done with username/password, JWT, or OAuth2.

---

### 43. Difference between Authentication and Authorization?
**Answer:**  
- **Authentication**: Verifying identity (login).  
- **Authorization**: Deciding what the user can access (roles, permissions).  

---

### 44. What is CSRF and how do you prevent it?
**Answer:**  
CSRF is Cross-Site Request Forgery, where malicious sites trick users into submitting requests.  
Prevention: CSRF tokens, SameSite cookies.

---

### 45. What is XSS and how do you prevent it?
**Answer:**  
XSS is Cross-Site Scripting, injecting malicious scripts into web pages.  
Prevention: Input validation, escaping output, using libraries like OWASP ESAPI.

---

### 46. How does JWT authentication work?
**Answer:**  
JWT is a token containing user claims. Server validates it using a secret key. It allows stateless authentication without storing sessions.

---

### 47. Explain rate limiting in APIs.
**Answer:**  
Rate limiting restricts the number of requests per client. Implemented using token bucket, leaky bucket, or sliding window algorithms. Prevents abuse and ensures fair usage.

---

### 48. How do you monitor backend services?
**Answer:**  
Using tools like Prometheus, Grafana, ELK stack, or Zipkin. Monitor logs, metrics, tracing, and alerts for system health.

---

### 49. Explain Circuit Breaker Pattern.
**Answer:**  
Circuit breaker prevents cascading failures in microservices. If a service keeps failing, the breaker opens, and requests are stopped temporarily. Netflix Hystrix is a common implementation.

---

### 50. What are some best practices for writing scalable Java backend code?
**Answer:**  
- Use dependency injection.  
- Avoid tight coupling.  
- Apply caching.  
- Use async processing when possible.  
- Write tests and monitor performance.  
- Follow SOLID principles.

---
