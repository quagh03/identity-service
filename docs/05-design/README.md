# Design

How a part of the service works inside the [architecture](../04-architecture/README.md).

| Folder | File these here |
| --- | --- |
| [domain](domain/README.md) | Concepts the service owns, their rules, and their lifecycle |
| [security](security/README.md) | Authentication, authorization, sessions, tokens, keys, clients, trust boundaries |
| [data](data/README.md) | Persistence, transactions, Flyway migrations, retention |
| [flows](flows/README.md) | One trigger through to an outcome, including failures |
| [integrations](integrations/README.md) | Systems outside this process |

`DES` files use [the design template](../00-handbook/templates/design.md) and live in `domain`, `security`, `data`, or `integrations`. `FLOW` files use [the flow template](../00-handbook/templates/flow.md) and live in `flows`. The index for both prefixes is this page, so a reader can see the whole design in one table.

A database table is data design. A caller-visible payload is a [contract](../06-contracts/README.md). The reason for a hard choice is a [decision](../03-decisions/README.md).

When you add a file, add a row here and a row in [traceability](../09-quality/traceability.md).

| ID | Title | Status | Updated |
| --- | --- | --- | --- |
| | No design yet. | | |
