# Sentiric DB Models

**Description:** This repository contains shared database schemas and ORM models for common data used across multiple Sentiric services, where a shared database approach is adopted for specific datasets.

**Core Responsibilities:**
*   Defining centralized database schema definitions (e.g., SQL migration scripts, ORM entity definitions).
*   Providing models for common reference data.

**Technologies:**
*   SQL (for schema definitions)
*   ORM libraries (e.g., TypeORM for Node.js, SQLAlchemy for Python, Gorm for Go)
*   Database migration tools (e.g., Flyway, Liquibase, Knex.js).

**Usage:**
This is **not a running service**; it's a **library/schema definition repository**. Services that share a database will include this repository as a dependency to ensure consistency in data access and schema management.
**Note:** In a pure microservice architecture, each service typically owns its own database. This repository is primarily useful if specific datasets are deliberately shared for pragmatic reasons.

**Local Development:**
1.  Clone this repository: `git clone https://github.com/sentiric/sentiric-db-models.git`
2.  Navigate into the directory: `cd sentiric-db-models`
3.  (Optional: If you have migration tools configured) Run database migrations: `npm run migrate` (or equivalent).

**Deployment:**
Not applicable as this is not a deployable service. Database schema changes here require careful coordination with dependent services and their deployments.

**Contributing:**
We welcome contributions! Please refer to the [Sentiric Governance](https://github.com/sentiric/sentiric-governance) repository for coding standards and contribution guidelines. Changes to database models require careful review due to their critical impact.

**License:**
This project is licensed under the [License](LICENSE).
