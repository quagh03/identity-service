# Architecture

The shape that other documents assume: who is outside this service, how code is divided, which direction dependencies may point, and what one deployment contains.

Living pages. Edit them in place. A single expensive choice that produced this shape is also an [ADR](../03-decisions/README.md); this folder holds the map, and the ADR holds the reason.

Add a page when the content is real:

| Page | Contents |
| --- | --- |
| `context.md` | People and systems that call this service, and systems it calls |
| `modules.md` | Spring Modulith modules, what each owns, and allowed dependencies |
| `deployment.md` | Processes and datastores inside one deployment |

How to ship a build is [operations](../08-operations/README.md). How a module behaves internally is [design](../05-design/README.md).

No architecture pages yet. Modulith is a dependency. Module names are not chosen.
