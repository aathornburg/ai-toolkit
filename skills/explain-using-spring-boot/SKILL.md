---
name: explain-using-spring-boot
description: Explain Node/Express backend code using Java Spring Boot analogies
---

Name: explain-using-spring-boot

Purpose
-------
Provide Spring Boot-style explanations for TypeScript/JavaScript backend code by mapping Express and Node patterns to Spring Boot concepts.

When to use
-----------
- The code contains backend routing, dependency injection, validation, or database access.
- The user wants Java/Spring Boot analogies for Node/Express architecture.

Behavior
--------
- Map Express app startup to `@SpringBootApplication` and `SpringApplication.run()`.
- Explain router/controller mapping as `@RestController`, `@RequestMapping`, and method-level request mappings.
- Relate service modules to Spring `@Service` beans and dependency injection wiring.
- Compare validation with Spring `@Valid` and DTO validation.
- Align database client/config patterns to Spring Data/JPA configuration.
