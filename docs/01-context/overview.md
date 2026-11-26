# Overview

Status: living. Facts about this repository. Product scope is not decided. When it is, add `scope.md` in this folder and cite it from requirements.

## Identity

| | |
| --- | --- |
| Name | identity-service |
| Group | `com.huylq` |
| Version | `0.0.1-SNAPSHOT` |
| Description | identity-service |
| Entry point | `src/main/java/com/huylq/identityservice/IdentityServiceApplication.java` |

## Stack

Declared in `build.gradle`.

| Piece | What the build uses |
| --- | --- |
| Java | 27 |
| Spring Boot | 4.2.0 |
| Spring Modulith | BOM 2.2.0, `spring-modulith-starter-jpa` |
| Web | `spring-boot-starter-webmvc` |
| Persistence | `spring-boot-starter-data-jpa`, PostgreSQL driver |
| Migrations | `spring-boot-starter-flyway`, `flyway-database-postgresql` |
| Security | `spring-boot-starter-security`, OAuth2 authorization server |
| Local development | Lombok, Spring Boot DevTools |

## What is in the tree today

- One application class. No domain types, HTTP endpoints, security configuration, or Modulith modules yet.
- `src/main/resources/application.yaml` sets `spring.application.name` to `identity-service`.
- One test, `src/test/java/com/huylq/identityservice/IdentityServiceApplicationTests.java`, that loads the Spring context.
- Gradle wrapper. Project name is set in `settings.gradle`.

## Where the rest is written

| Topic | Folder |
| --- | --- |
| Required behavior | [Requirements](../02-requirements/README.md) |
| Hard choices | [Decisions](../03-decisions/README.md) |
| Boundaries and deployment shape | [Architecture](../04-architecture/README.md) |
| Domain, security, data, flows | [Design](../05-design/README.md) |
| HTTP, events, errors | [Contracts](../06-contracts/README.md) |
| Build and test | [Engineering](../07-engineering/README.md) |
| Configure, run, recover | [Operations](../08-operations/README.md) |
