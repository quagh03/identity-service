# Conventions

Status: living.

Two kinds of pages live in `docs`:

| Kind | Examples | How it changes |
| --- | --- | --- |
| Living | Overview, glossary, this page, folder indexes, architecture maps, engineering guides | Edit in place. No ID. |
| Tracked | Requirements, decisions, designs, flows, contracts, runbooks | Stable ID. Status field. Accepted meaning changes by superseding, not by a silent rewrite. |

## IDs

| Prefix | Means | Folder |
| --- | --- | --- |
| `REQ` | Requirement | `02-requirements` |
| `ADR` | Decision | `03-decisions` |
| `DES` | Design | `05-design` (`domain`, `security`, `data`, `integrations`) |
| `FLOW` | Flow | `05-design/flows` |
| `API` | HTTP contract | `06-contracts/http` |
| `EVT` | Event contract | `06-contracts/events` |
| `ERR` | Error contract | `06-contracts/errors` |
| `RUN` | Runbook | `08-operations/runbooks` |
| `Q` | Open question | A row in `09-quality/open-questions.md` only |

Rules:

- Four digits, starting at `0001`. Example: `REQ-0001`.
- `0000` is reserved for templates. It never appears in an index.
- Never reuse an ID. Never renumber. Gaps are fine.
- The filename is `{ID}-{kebab-case-title}.md`. Example: `REQ-0001-issue-access-token.md`.
- Questions are rows, not files. A long investigation is a [record](../10-records/README.md); the question row links to it.

## Status

Every tracked document has one status in its front matter.

| Status | Meaning |
| --- | --- |
| `draft` | Being written. Not a source of truth. |
| `proposed` | Ready for review. |
| `accepted` | Source of truth. |
| `superseded` | Replaced. The file stays. `superseded_by` points at the replacement. |
| `rejected` | Considered and declined. The file stays so the reason stays findable. |

Accepted meaning is the behavior, the choice, or the caller-visible shape. Clarifying a sentence keeps the same ID and updates `updated`. Changing that meaning adds a new ID and marks the old document `superseded`.

## Front matter

Tracked documents start with:

```yaml
---
id: REQ-0001
title: Short title
status: draft
created: YYYY-MM-DD
updated: YYYY-MM-DD
supersedes: []
superseded_by:
relates: []
code: []
---
```

- `relates` lists other IDs. The prose says how they relate.
- `code` lists repository paths that implement or verify the document, such as `src/main/java/com/huylq/identityservice/...`. Update the path when the code moves.
- `superseded_by` is empty until another document replaces this one.

## Where a fact goes

| You are recording | Write |
| --- | --- |
| Why the project exists, scope, words | Living page under `01-context` |
| A need and how to tell it is met | `REQ` |
| A choice that would be expensive to reverse, and the reason | `ADR` |
| System context, module boundaries, dependency direction, deployable shape | Living page under `04-architecture` |
| How something works inside those boundaries | `DES` |
| One trigger through to an outcome, including failures | `FLOW` |
| Something a caller or another module can rely on | `API`, `EVT`, or `ERR` |
| How to build and test | Living page under `07-engineering` |
| How to configure, ship, or recover | Living page under `08-operations`, or a `RUN` |
| A spike, a comparison, a scratch note | Record under `10-records` |
| Something unresolved | A `Q` row |

A record never overrides an accepted document. Promote the conclusion into a tracked or living page, then link the record from there.

## Integrity

- An `accepted` document relates only to other `accepted` documents, or to living pages.
- `draft` and `proposed` may relate to anything.
- An `accepted` contract names the `accepted` requirement it fulfills.
- A `superseded` or `rejected` document keeps its file and its ID.
- If two accepted documents disagree, fix both in the same change. Do not pick a winner in conversation and leave the files in conflict.
- Diagrams are [Mermaid](https://mermaid.js.org/) in the document, with the document ID in the diagram title or the paragraph above it.

## Adding a document

1. Copy the template from `00-handbook/templates/`.
2. Take the next free ID for that prefix. Check the area index and [traceability](../09-quality/traceability.md).
3. Write the document.
4. Add a row to the area index:

   | Prefix | Index |
   | --- | --- |
   | `REQ` | `02-requirements/README.md` |
   | `ADR` | `03-decisions/README.md` |
   | `DES`, `FLOW` | `05-design/README.md` |
   | `API`, `EVT`, `ERR` | `06-contracts/README.md` |
   | `RUN` | `08-operations/runbooks/README.md` |

5. Add a row to [traceability](../09-quality/traceability.md).
6. Update `relates` on the documents you touched.

## Links

Use relative Markdown links. Put the ID in the link text: `[REQ-0001](../02-requirements/REQ-0001-issue-access-token.md)`.

Living pages are linked by path. Cite a heading when a single section is the target.
