# Workflow and validation

[Back to project](../README.md)

## Observable job states

| State | Operator interpretation |
| --- | --- |
| Queued | The request was accepted and is waiting for execution |
| Running | The browser workflow is in progress |
| Finished | The workflow recorded a successful result |
| Failed | Review the reason and available debugging evidence |

An accepted HTTP request and a completed business operation are separate events. The interface needs to communicate both.

## Documented behavior

The [public reference](https://saraward.ai/bookingbot-docs-portfolio.html) documents multipart file intake, required booking fields, duplicate in-flight request handling, job polling, debug capture, and health reporting. It uses anonymized company and user details.

## Sandbox verification plan

These are review scenarios, **not results claimed from this curation**:

| Scenario | Expected observation |
| --- | --- |
| Missing required input or line sheet | The request fails validation before a booking starts |
| Valid synthetic booking | A job ID is returned and status reaches a terminal state |
| Duplicate request during execution | The existing job is returned |
| Business validation failure | Failed status includes a useful reason |
| Changed or missing page element | Debugging evidence helps identify the failing stage |
| Deployment change | Health/version evidence identifies the running build |

Tests that drive a browser into an operational system belong in an authorized sandbox with synthetic records. No live bookings were created while preparing this showcase.

## Operational handoff

A complete handoff should identify the owner, required configuration, environment boundaries, user instructions, error recovery, deployment checks, and the process for updating automation when the underlying UI changes. The public sample demonstrates the documentation structure; private deployment details stay with the application owner.
