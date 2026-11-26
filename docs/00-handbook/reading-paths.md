# Reading paths

Status: living.

Open the first file on the path. Follow links when you need depth.

## I am new to the repository

1. [Docs home](../README.md)
2. [Overview](../01-context/overview.md)
3. [Conventions](conventions.md), skim the ID and status rules
4. The indexes under `02` through `06` as those folders fill in

## I am designing the service

Write in this order. When a question blocks the next page, add a row to [open questions](../09-quality/open-questions.md) and continue with a part you can settle.

1. Scope and goals as living pages in [context](../01-context/README.md)
2. Requirements for behavior you can state and check
3. Decisions for choices that are expensive to reverse
4. Architecture: context, modules, deployment shape
5. Design: domain, security, and data, then flows
6. Contracts that match the design
7. Engineering and operations pages once the steps are real

A design may stay `draft` while the set is incomplete. A contract becomes `accepted` together with the requirement it fulfills.

## I need to change behavior

1. Find the ID in [traceability](../09-quality/traceability.md) or the area index.
2. Read the requirement and the contract together.
3. When the change reverses a choice, add a decision and mark the old one `superseded`.
4. Update the design, the contract, and the code in the same change.
5. Refresh `relates`, the area index, and the traceability row.

## I need to know why something is the way it is

1. [Decisions](../03-decisions/README.md)
2. The design that decision relates
3. A [record](../10-records/README.md) only when the decision links one

## I need to run or recover the service

1. [Operations](../08-operations/README.md)
2. The runbook whose symptom matches
3. [Engineering](../07-engineering/README.md) for a local build
