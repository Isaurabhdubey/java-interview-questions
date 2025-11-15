# Java & Spring Boot Interview Preparation README

This repository contains detailed notes, explanations, and code snippets covering important core Java, Spring Boot, microservices, and system design concepts. It also includes practice programming questions frequently asked in interviews.

---

## 1. OOPs Concepts (with Real-Time Implementation)

### **Inheritance**

Used in my project for extending a base `AuditEntity` for all JPA entities.

```java
public class AuditEntity {
    private LocalDateTime createdAt;
    private LocalDateTime updatedAt;
}

public class Customer extends AuditEntity {
    private String name;
}
```

### **Polymorphism**

Used in strategy pattern for payment calculations.

```java
interface PaymentService { void pay(); }
class CardPayment implements PaymentService { public void pay(){} }
class UpiPayment implements PaymentService { public void pay(){} }
```

### **Encapsulation**

Used in DTOs and models.

```java
public class UserDto {
    private String username;
    public String getUsername(){return username;}
    public void setUsername(String u){this.username=u;}
}
```

---

## 2. SOLID Principles

* **S**ingle Responsibility
* **O**pen Closed
* **L**iskov Substitution
* **I**nterface Segregation
* **D**ependency Inversion

---

## 3. Collections

### Common Collections Worked Recently

* ArrayList
* LinkedList
* HashMap
* TreeMap
* HashSet
* ConcurrentHashMap
* CopyOnWriteArrayList

### a. Why ArrayList over LinkedList?

* Faster random access (O(1))
* Better cache locality

### b. HashMap Internal Flow

* Uses array + linked list + tree (since Java 8)
* TreeNode used when bucket size > 8

### HashMap vs TreeMap

* HashMap → fast, no ordering
* TreeMap → sorted keys (Red-Black Tree)

### d. Concurrent Collections

* **ConcurrentHashMap** → segment locking
* **CopyOnWriteArrayList** → safe for read-heavy use cases

### e. ArrayList vs CopyOnWriteArrayList

* COWAL duplicates array on write → expensive for writes

---

## 4. Multithreading Concepts

### a. Synchronization

Used to avoid race conditions.

### b. When to Use Sleep vs Wait

* `sleep()` → pause thread
* `wait()` → release lock and pause

### c. Concurrent thread handling

### d. Async

### e. ExecutorService

```java
ExecutorService service = Executors.newFixedThreadPool(10);
```

### f. CompletableFuture

### g. ExecutorService vs CompletableFuture

* CompletableFuture supports chaining & async pipelines

---

## 5. Runnable, Thread, Callable

* Runnable → no return
* Callable → returns value

---

## 6–7. Serialization & Serializable

Used for caching, session sharing.

```java
class User implements Serializable {}
```

---

## 8. Singleton (Used in Project)

Used for configuration loader.

---

## 9. Design Patterns Used in Project

* Singleton
* Factory
* Builder
* Strategy
* Observer
* Circuit Breaker

---

## 10. @Controller vs @RestController

* `@Controller` → returns views
* `@RestController` → returns JSON

---

## 11. @Bean

Used to create custom beans.

## 12. Dependency Injection

Constructor-based recommended.

## 13. SOLID (duplicate reference)

Already covered.

---

## 14. How Spring Works Internally

* IOC Container
* Bean Creation → DI → Initialization → Ready

---

## 15. Microservices

* Independent deployable units
* Communication through REST / MQ

---

## 16. HTTP Methods

GET, POST, PUT, PATCH, DELETE

---

## 17. RestTemplate & Alternatives

* WebClient
* Feign Client
* gRPC

---

## 18. Handling Microservice Failures

* Retries
* Circuit Breaker (Resilience4J)
* Fallback
* Timeouts
* Bulkhead

---

## 19. Spring Security (OAuth2, JWT)

JWT for authentication between microservices.

---

## 20. JVM Architecture

* ClassLoader
* Memory Areas
* Execution Engine
* Garbage Collector

---

## 21. Spring Bean Scopes

* Singleton
* Prototype
* Request
* Session

---

## 22. Setter vs Constructor Injection

Constructor preferred for immutability.

---

## 23. Spring JPA

Entity, Repository, JPQL, Criteria API

---

## 24. Profile

Used to activate environment-specific configs.

---

## 25. @Qualifier

Used when multiple beans of same type exist.

---

## 26. @Value

Inject properties.

---

## 27. PreAuth, PostAuth, Interceptors

PreAuth used for method-level security.

---

## 28. Spring Security Filter Chain

* Authentication filters
* Authorization filters

---

## 29. Microservice Communication

* REST
* RabbitMQ/Kafka
* gRPC

---

## 30. API Gateway

* Routing
* Authentication
* Logging
* Rate limiting

---

## 31. Starvation

When one service is slow → thread pool blocked
Solution: timeouts, circuit breaker

---

## 32. Circuit Breaking

Resilience4J → open, half-open, closed.

---

## 33. Retryable, Fallback

Used via Resilience4J or Spring Retry.

---

## 34. Stream API (Detailed)

map, filter, reduce, sorted, collect

---

## 35. Optional & Generics

Avoid nulls, type safety.

---

# Practice Coding Questions

1. Average List
2. Calculate Sum
3. Count String
4. Occurrence of Character
5. Count Subarray
6. Duplicate String
7. Final vs Static
8. Peak Element
9. Second Largest & Smallest
10. LinkedHashSet Example
11. Min and Max
12. Longest Palindrome
13. Longest Common Prefix
14. Sorting
15. Searching

---

