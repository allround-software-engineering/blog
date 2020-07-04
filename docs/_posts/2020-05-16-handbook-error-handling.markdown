---
layout: post
title:  "Engineering Handbook: Error Handling"
date:   2020-05-16 06:48:50 -0700
categories: allround software engineering handbook error handling
published: true
---

## Why handle error?

Software runs in real world. Therefore, software will encounter various less-than-ideal situations:

- User could enter invalid data.
- Hard-drive can fail.
- Network connections can be disrupted. E.g. [submarine network cable cut by ship anchor.](https://en.wikipedia.org/wiki/2008_submarine_cable_disruption)

Correct software behavior must define handling logic for all possible error situations.

All actual code implementation will handle all error in some way, either explicit or implicit.

Examples of explicit error handling:
- Catching an exception and show an error message to user then return to some known state.
- Test an HTTP REST API call's response code and handle specific error codes like HTTP 400.

Example of implicit error handling:
- Relying on JVM's exit-on-unhandled exception behavior to exit on any exception.
- Retry API call if it fails for some unknown error.

In practice, it is impossible and not economical to fully enumerate all possible error situations and handle them explicitly. Therefore, we need to make use of both explicit and implicit error handling.

## Terminology

- Operation: Some action that should be performed. E.g. saving data to database / querying calendar events.
- Upstream: Operation requester. AKA API client. AKA Data Source.
- Downstream: Operation performer. AKA API server. AKA Data Sink.
- Request: Self-contained data describing the operation to be performed.
- Response: Self-contained data describing the outcome of the operation. (Could be success or failure.)

## Source of errors

Situations where error could happen:

- API calls
    - E.g. calling another method, RPC, HTTP requests, Database operations. (Downstream failed to perform operation. AKA Failed operation.)
- Data pipeline
    - Data collected from user fails to pass predefined validation check. (Upstream provided invalid data. AKA Invalid ata.)
- Logical state transition
    - User attempts to perform invalid state transition. (Upstream made an request that is impossible to perform. AKA Invalid request.)

## Error definition and categorization

- Do you control both side of the API call? Do you control the data source or request source?
- Is the operation expensive? e.g. costing upstream money / causing downstream to perform significant amount of computation/storage.
- Does the upstream actually care enough to do something more elaborate than standard error definitions?

Only use a more elaborate error categorization if you answer "yes" to all questions. You should use the standard error definition and categorization in vast majority of the case.

## Standard error definition and categorization #StandardErrorDefinition@2020

Error

- Success / No error
- Non-retryable Error (Upstream fault, Invalid Data or Invalid request)
- Non-retryable Error (Downstream fault, downstream decided to stop supporting some operation)
- Retryable Error (Failed Operation. Always downstream fault. Downstream could be too busy.)

## Designs that will simplify error handling

- Idempotent operations.
- Request with ID.

