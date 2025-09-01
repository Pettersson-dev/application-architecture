# Application Architecture  
**Opinionated Guide to Fit-for-Purpose Application Design**  

---

## Prerequisites  
- **Architecture Context**: Microservice and event-driven architecture, enabled by service mesh and polyglot support.  
- **Application Types**:  
  - Progressive Web Applications (PWA)  
  - Single Page Applications (SPA)  
  - Backend-for-Frontend (BFF)  
  - Domain-driven backend services  
- **Related Resources**:  
  - [Security Architecture](https://github.com/pettersson-dev/security-architecture)  
  - [API Integration Architecture](https://github.com/Pettersson-dev/Integration-architecture/blob/main/api-integration.md)  
  - [Programming Language Decision Guide](https://github.com/pettersson-dev/programming-language-decision-guide)  

---

## Application Layers  

### Client Layer  
- **Browser Applications** → SPA or PWA with JavaScript/TypeScript.  
- **Mobile Applications** → Native (Swift/Kotlin) or cross-platform depending on differentiation needs.  
- **BFF (Backend-for-Frontend)** → Thin APIs tailored to specific frontend channels.  

---

### Service Layer  
- **Domain Services** → Implement bounded contexts via microservices.  
- **Integration Services** → Handle external APIs and legacy systems.  
- **Orchestration & Composition** → Expose aggregated functionality across multiple services.  

---

### Data Layer  
- **Polyglot Persistence** → Choose database per use case (SQL, NoSQL, Graph, Time-series).  
- **Event Stores** → Capture domain events for auditing and replay.  
- **Caching** → Reduce latency and improve performance for read-heavy workloads.  
- **Data Mesh Principles** → Federated ownership of domain data products.  

---

## Cross-Cutting Concerns  

- **Security**  
  - Zero Trust principles across services.  
  - Secure APIs with authentication, authorization, and rate limiting.  

- **Observability**  
  - Centralized logging and metrics.  
  - Distributed tracing across microservices.  
  - Alerts integrated into incident management.  

- **Scalability & Resilience**  
  - Horizontal scaling of stateless services.  
  - Circuit breakers, retries, and bulkheads.  
  - Chaos engineering to validate resilience.  

- **DevOps & Automation**  
  - Continuous integration and delivery (CI/CD).  
  - Infrastructure as Code (IaC) for repeatability.  
  - Automated testing across all layers.  

---

## Decision Tree  

Start  
│  
├── Is it **User-Facing**?  
│   ├── Web → SPA/PWA (TypeScript/React/Vue/Angular)  
│   └── Mobile  
│        ├── iOS → Swift  
│        └── Android → Kotlin  
│  
└── Is it **Backend**?  
    ├── Domain service → Microservice (Go, Java/Kotlin, C#)  
    ├── Data-heavy/ML → Python  
    ├── High-performance & secure → Rust  
    └── Realtime concurrent → Elixir/Erlang  

---

## Cross-Cutting Principles  

- **Separation of Concerns** → Clear boundaries between frontend, backend, and data.  
- **Polyglot Architecture** → Choose the right tool/language for each bounded context.  
- **Loose Coupling, High Cohesion** → Services should do one thing well.  
- **API-First** → All interactions exposed via APIs, versioned and documented.  
- **Event-Driven** → Prefer async messaging for decoupling.  
- **Resilience by Design** → Assume failure and design graceful degradation.  

---

## Summary  
- **Client Layer** → SPA/PWA for web, Swift/Kotlin for mobile.  
- **Service Layer** → Microservices mapped to bounded contexts.  
- **Data Layer** → Polyglot persistence with event sourcing and caching.  
- **Cross-Cutting** → Security, observability, scalability, and automation baked in.  