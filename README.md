# MailFlow  
*A modular Spring Boot mail system simulating end-to-end email delivery.*

---

## 📖 Overview
MailFlow is a **Spring Boot–based mail delivery system** designed to simulate how real-world mail servers handle sending, receiving, validating, and storing emails — starting as a **monolithic architecture** and later evolving into a **microservices-based system**.

The goal is to build a **clear, educational project** that demonstrates:
- User account creation and authentication
- Mail sending and receiving flow within a single domain (`@test.com`)
- Validation, spam checking, and persistence of mail data
- Progressive transition from a monolith → microservices architecture


## 🏗️ Architecture Plan

### **Phase 1 – Monolith**
- All services live inside a single Spring Boot application.
- Shared database connection pool.
- Endpoints are logically separated.
- Each internal service (validator, sender, etc.) exists as its own Java class.
- Internal communication via direct method calls.

### **Phase 2 – Microservices Transition**
- Gradually split each major component into independent Spring Boot services
- Inter-service communication via REST (HTTP) or gRPC.
- Shared or independent databases per service, based on use case.

---

## ⚙️ Tech Stack
- **Language:** Java  
- **Framework:** Spring Boot  
- **Database:** H2 / PostgreSQL (configurable)  
- **SMTP:** JavaMail / Spring Mail abstraction  
- **Build Tool:** Maven or Gradle  
- **Architecture:** Monolith → Microservices evolution  

---

