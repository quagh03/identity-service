# Contracts

What another party can rely on. If a design and a contract disagree, update both in the same change. Callers are held to the contract.

| Folder | Prefix | File these here |
| --- | --- | --- |
| [http](http/README.md) | `API` | Resources and operations this service exposes, and HTTP calls it makes |
| [events](events/README.md) | `EVT` | Modulith events between modules, and events published outside the process |
| [errors](errors/README.md) | `ERR` | Stable error identifiers a caller can branch on |

Copy [the contract template](../00-handbook/templates/contract.md). One resource, one event family, or one error family per file. Set the `id` prefix to match the folder.

When you add a file, add a row here and a row in [traceability](../09-quality/traceability.md).

| ID | Title | Status | Updated |
| --- | --- | --- | --- |
| | No contracts yet. | | |
