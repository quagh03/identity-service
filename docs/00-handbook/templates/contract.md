> Template. Copy to `docs/06-contracts/http/`, `events/`, or `errors/`. Replace the prefix and `0000` with `API`, `EVT`, or `ERR` and the next free ID. Do not index this file.

```yaml
---
id: API-0000
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

# API-0000 Short title

## Audience

Who relies on this: an external caller, another service, or a Spring Modulith module.

## Shape

The method and path, the event name, or the error identifier. Include the payload and the success status. One resource or one event family per file when the operations share a model.

## Authentication and authorization

What the caller must present, and which permission or scope applies. The mechanism itself is a security design page.

## Errors

`ERR` IDs a caller can branch on. HTTP status lives here; the shared error body lives on the `ERR` page.

## Trace

The requirement this fulfills, the flow that exercises it, and the code path.
